# 🗃️ Cache

* [Introduction](https://laravel.com/docs/11.x/cache#introduction)
* [Configuration](https://laravel.com/docs/11.x/cache#configuration)
  * [Driver Prerequisites](https://laravel.com/docs/11.x/cache#driver-prerequisites)
* [Cache Usage](https://laravel.com/docs/11.x/cache#cache-usage)
  * [Obtaining a Cache Instance](https://laravel.com/docs/11.x/cache#obtaining-a-cache-instance)
  * [Retrieving Items From the Cache](https://laravel.com/docs/11.x/cache#retrieving-items-from-the-cache)
  * [Storing Items in the Cache](https://laravel.com/docs/11.x/cache#storing-items-in-the-cache)
  * [Removing Items From the Cache](https://laravel.com/docs/11.x/cache#removing-items-from-the-cache)
  * [The Cache Helper](https://laravel.com/docs/11.x/cache#the-cache-helper)
* [Atomic Locks](https://laravel.com/docs/11.x/cache#atomic-locks)
  * [Managing Locks](https://laravel.com/docs/11.x/cache#managing-locks)
  * [Managing Locks Across Processes](https://laravel.com/docs/11.x/cache#managing-locks-across-processes)
* [Adding Custom Cache Drivers](https://laravel.com/docs/11.x/cache#adding-custom-cache-drivers)
  * [Writing the Driver](https://laravel.com/docs/11.x/cache#writing-the-driver)
  * [Registering the Driver](https://laravel.com/docs/11.x/cache#registering-the-driver)
* [Events](https://laravel.com/docs/11.x/cache#events)

### [Introduction](https://laravel.com/docs/11.x/cache#introduction) <a href="#introduction" id="introduction"></a>

Some of the data retrieval or processing tasks performed by your application could be CPU intensive or take several seconds to complete. When this is the case, it is common to cache the retrieved data for a time so it can be retrieved quickly on subsequent requests for the same data. The cached data is usually stored in a very fast data store such as [Memcached](https://memcached.org/) or [Redis](https://redis.io/).

Thankfully, Laravel provides an expressive, unified API for various cache backends, allowing you to take advantage of their blazing fast data retrieval and speed up your web application.

### [Configuration](https://laravel.com/docs/11.x/cache#configuration) <a href="#configuration" id="configuration"></a>

Your application's cache configuration file is located at `config/cache.php`. In this file, you may specify which cache store you would like to be used by default throughout your application. Laravel supports popular caching backends like [Memcached](https://memcached.org/), [Redis](https://redis.io/), [DynamoDB](https://aws.amazon.com/dynamodb), and relational databases out of the box. In addition, a file based cache driver is available, while `array` and "null" cache drivers provide convenient cache backends for your automated tests.

The cache configuration file also contains a variety of other options that you may review. By default, Laravel is configured to use the `database` cache driver, which stores the serialized, cached objects in your application's database.

#### [Driver Prerequisites](https://laravel.com/docs/11.x/cache#driver-prerequisites) <a href="#driver-prerequisites" id="driver-prerequisites"></a>

[**Memcached**](https://laravel.com/docs/11.x/cache#memcached)

Using the Memcached driver requires the [Memcached PECL package](https://pecl.php.net/package/memcached) to be installed. You may list all of your Memcached servers in the `app/etc/env.php` configuration file. This file already contains a `memcached.servers` entry to get you started:

```
MEMCACHED_HOST='/var/run/memcached/memcached.sock' || '127.0.0.1'
MEMCACHED_PORT= 0 || 11211
#MEMCACHED_WEIGHT=100
```

[**Redis**](https://laravel.com/docs/11.x/cache#redis)

Before using a Redis cache with Laravel, you will need to either install the PhpRedis PHP extension via PECL or install the `predis/predis` package (\~2.0) via Composer.

For more information on configuring Redis, consult its [Maginium documentation page](redis.md).

[**DynamoDB**](https://laravel.com/docs/11.x/cache#dynamodb)

Before using the [DynamoDB](https://aws.amazon.com/dynamodb) cache driver, you must create a DynamoDB table to store all of the cached data. Typically, this table should be named `cache`. However, you should name the table based on the value of the `stores.dynamodb.table` configuration value within the `cache` configuration file. The table name may also be set via the `DYNAMODB_CACHE_TABLE` environment variable.

This table should also have a string partition key with a name that corresponds to the value of the `stores.dynamodb.attributes.key` configuration item within your application's `cache` configuration file. By default, the partition key should be named `key`.

Typically, DynamoDB will not proactively remove expired items from a table. Therefore, you should [enable Time to Live (TTL)](https://docs.aws.amazon.com/amazondynamodb/latest/developerguide/TTL.html) on the table. When configuring the table's TTL settings, you should set the TTL attribute name to `expires_at`.

Next, install the AWS SDK so that your Laravel application can communicate with DynamoDB:

```
composer require aws/aws-sdk-php
```

In addition, you should ensure that values are provided for the DynamoDB cache store configuration options. Typically these options, such as `AWS_ACCESS_KEY_ID` and `AWS_SECRET_ACCESS_KEY`, should be defined in your application's `.env` configuration file:

```
# AWS Creds.
AWS_ACCESS_KEY_ID=
AWS_SECRET_ACCESS_KEY=
AWS_DEFAULT_REGION=us-east-1

# DynamoDB Configs.
DYNAMODB_CACHE_TABLE=cache
DYNAMODB_ENDPOINT=
```

[**MongoDB**](https://laravel.com/docs/11.x/cache#mongodb)

If you are using MongoDB, a `mongodb` cache driver is provided by the official `mongodb/laravel-mongodb` package and can be configured using a `mongodb` database connection. MongoDB supports TTL indexes, which can be used to automatically clear expired cache items.

For more information on configuring MongoDB, please refer to the MongoDB [Cache and Locks documentation](https://www.mongodb.com/docs/drivers/php/laravel-mongodb/current/cache/).

### [Cache Usage](https://laravel.com/docs/11.x/cache#cache-usage) <a href="#cache-usage" id="cache-usage"></a>

#### [Obtaining a Cache Instance](https://laravel.com/docs/11.x/cache#obtaining-a-cache-instance) <a href="#obtaining-a-cache-instance" id="obtaining-a-cache-instance"></a>

To obtain a cache store instance, you may use the `Cache` facade, which is what we will use throughout this documentation. The `Cache` facade provides convenient, terse access to the underlying implementations of the Laravel cache contracts:

```
<?php
 
namespace App\Http\Controllers;
 
use Illuminate\Support\Facades\Cache;
 
class UserController extends Controller
{
    /**
     * Show a list of all users of the application.
     */
    public function index(): array
    {
        $value = Cache::get('key');
 
        return [
            // ...
        ];
    }
}
```

[**Accessing Multiple Cache Stores**](https://laravel.com/docs/11.x/cache#accessing-multiple-cache-stores)

Using the `Cache` facade, you may access various cache stores via the `store` method. The key passed to the `store` method should correspond to one of the stores listed in the `stores` configuration array in your `cache` configuration file:

```
$value = Cache::store('file')->get('foo');
 
Cache::store('redis')->put('bar', 'baz', 600); // 10 Minutes
```

#### [Retrieving Items From the Cache](https://laravel.com/docs/11.x/cache#retrieving-items-from-the-cache) <a href="#retrieving-items-from-the-cache" id="retrieving-items-from-the-cache"></a>

The `Cache` facade's `get` method is used to retrieve items from the cache. If the item does not exist in the cache, `null` will be returned. If you wish, you may pass a second argument to the `get` method specifying the default value you wish to be returned if the item doesn't exist:

```
$value = Cache::get('key');
 
$value = Cache::get('key', 'default');
```

You may even pass a closure as the default value. The result of the closure will be returned if the specified item does not exist in the cache. Passing a closure allows you to defer the retrieval of default values from a database or other external service:

```
$value = Cache::get('key', function () {
    return DB::table(/* ... */)->get();
});
```

[**Determining Item Existence**](https://laravel.com/docs/11.x/cache#determining-item-existence)

The `has` method may be used to determine if an item exists in the cache. This method will also return `false` if the item exists but its value is `null`:

```
if (Cache::has('key')) {
    // ...
}
```

[**Incrementing / Decrementing Values**](https://laravel.com/docs/11.x/cache#incrementing-decrementing-values)

The `increment` and `decrement` methods may be used to adjust the value of integer items in the cache. Both of these methods accept an optional second argument indicating the amount by which to increment or decrement the item's value:

```
// Initialize the value if it does not exist...
Cache::add('key', 0, now()->addHours(4));
 
// Increment or decrement the value...
Cache::increment('key');
Cache::increment('key', $amount);
Cache::decrement('key');
Cache::decrement('key', $amount);
```

[**Retrieve and Store**](https://laravel.com/docs/11.x/cache#retrieve-store)

Sometimes you may wish to retrieve an item from the cache, but also store a default value if the requested item doesn't exist. For example, you may wish to retrieve all users from the cache or, if they don't exist, retrieve them from the database and add them to the cache. You may do this using the `Cache::remember` method:

```
$value = Cache::remember('users', $seconds, function () {
    return DB::table('users')->get();
});
```

If the item does not exist in the cache, the closure passed to the `remember` method will be executed and its result will be placed in the cache.

You may use the `rememberForever` method to retrieve an item from the cache or store it forever if it does not exist:

```
$value = Cache::rememberForever('users', function () {
    return DB::table('users')->get();
});
```

[**Stale While Revalidate**](https://laravel.com/docs/11.x/cache#swr)

When using the `Cache::remember` method, some users may experience slow response times if the cached value has expired. For certain types of data, it can be useful to allow partially stale data to be served while the cached value is recalculated in the background, preventing some users from experiencing slow response times while cached values are calculated. This is often referred to as the "stale-while-revalidate" pattern, and the `Cache::flexible` method provides an implementation of this pattern.

The flexible method accepts an array that specifies how long the cached value is considered “fresh” and when it becomes “stale.” The first value in the array represents the number of seconds the cache is considered fresh, while the second value defines how long it can be served as stale data before recalculation is necessary.

If a request is made within the fresh period (before the first value), the cache is returned immediately without recalculation. If a request is made during the stale period (between the two values), the stale value is served to the user, and a [deferred function](https://laravel.com/docs/11.x/helpers#deferred-functions) is registered to refresh the cached value after the response is sent to the user. If a request is made after the second value, the cache is considered expired, and the value is recalculated immediately, which may result in a slower response for the user:

```
$value = Cache::flexible('users', [5, 10], function () {
    return DB::table('users')->get();
});
```

[**Retrieve and Delete**](https://laravel.com/docs/11.x/cache#retrieve-delete)

If you need to retrieve an item from the cache and then delete the item, you may use the `pull` method. Like the `get` method, `null` will be returned if the item does not exist in the cache:

```
$value = Cache::pull('key');
 
$value = Cache::pull('key', 'default');
```

#### [Storing Items in the Cache](https://laravel.com/docs/11.x/cache#storing-items-in-the-cache) <a href="#storing-items-in-the-cache" id="storing-items-in-the-cache"></a>

You may use the `put` method on the `Cache` facade to store items in the cache:

```
Cache::put('key', 'value', $seconds = 10);
```

If the storage time is not passed to the `put` method, the item will be stored indefinitely:

```
Cache::put('key', 'value');
```

Instead of passing the number of seconds as an integer, you may also pass an `DateTime` instance representing the desired expiration time of the cached item:

```
Cache::put('key', 'value', now()->addMinutes(10));
```

[**Store if Not Present**](https://laravel.com/docs/11.x/cache#store-if-not-present)

cache-store `add` method will only add the item to the cache if it does not already exist in the cache-store. The method will return `true` if the item is added to the cache. Otherwise, the method will return `false`. The `add` method is an atomic operation:

```
Cache::add('key', 'value', $seconds);
```

[**Storing Items Forever**](https://laravel.com/docs/11.x/cache#storing-items-forever)

The `forever` method may be used to store an item in the cache permanently. Since these items will not expire, they must be manually removed from the cache using the `forget` method:

```
Cache::forever('key', 'value');
```

If you are using the Memcached driver, items that are stored "forever" may be removed when the cache reaches its size limit.

#### [Removing Items From the Cache](https://laravel.com/docs/11.x/cache#removing-items-from-the-cache) <a href="#removing-items-from-the-cache" id="removing-items-from-the-cache"></a>

You may remove items from the cache using the `forget` method:

```
Cache::forget('key');
```

You may also remove items by providing a zero or negative number of expiration seconds:

```
Cache::put('key', 'value', 0);
 
Cache::put('key', 'value', -5);
```

You may clear the entire cache using the `flush` method:

```
Cache::flush();
```

Flushing the cache does not respect your configured cache "prefix" and will remove all entries from the cache. Consider this carefully when clearing a cache that is shared by other applications.

#### [The Cache Helper](https://laravel.com/docs/11.x/cache#the-cache-helper) <a href="#the-cache-helper" id="the-cache-helper"></a>

In addition to using the `Cache` facade, you may also use the global `cache` function to retrieve and store data via the cache. When the `cache` function is called with a single, string argument, it will return the value of the given key:

```
$value = cache('key');
```

If you provide an array of key/value pairs and an expiration time to the function, it will store values in the cache for the specified duration:

```
cache(['key' => 'value'], $seconds);
 
cache(['key' => 'value'], now()->addMinutes(10));
```

When the `cache` function is called without any arguments, it returns an instance of the `Illuminate\Contracts\Cache\Factory` implementation, allowing you to call other caching methods:

```
cache()->remember('users', $seconds, function () {
    return DB::table('users')->get();
});
```

When testing calls to the global `cache` function, you may use the `Cache::shouldReceive` method just as if you were [testing the facade](https://laravel.com/docs/11.x/mocking#mocking-facades).

### [Atomic Locks](https://laravel.com/docs/11.x/cache#atomic-locks) <a href="#atomic-locks" id="atomic-locks"></a>

To utilize this feature, your application must be using the `memcached`, `redis`, `dynamodb`, `database`, `file`, or `array` cache driver as your application's default cache driver. In addition, all servers must be communicating with the same central cache server.

#### [Managing Locks](https://laravel.com/docs/11.x/cache#managing-locks) <a href="#managing-locks" id="managing-locks"></a>

Atomic locks allow for the manipulation of distributed locks without worrying about race conditions. For example, [Laravel Forge](https://forge.laravel.com/) uses atomic locks to ensure that only one remote task is being executed on a server at a time. You may create and manage locks using the `Cache::lock` method:

```
use Illuminate\Support\Facades\Cache;
 
$lock = Cache::lock('foo', 10);
 
if ($lock->get()) {
    // Lock acquired for 10 seconds...
 
    $lock->release();
}
```

The `get` method also accepts a closure. After the closure is executed, Laravel will automatically release the lock:

```
Cache::lock('foo', 10)->get(function () {
    // Lock acquired for 10 seconds and automatically released...
});
```

If the lock is not available at the moment you request it, you may instruct Laravel to wait for a specified number of seconds. If the lock cannot be acquired within the specified time limit, an `Illuminate\Contracts\Cache\LockTimeoutException` will be thrown:

```
use Illuminate\Contracts\Cache\LockTimeoutException;
 
$lock = Cache::lock('foo', 10);
 
try {
    $lock->block(5);
 
    // Lock acquired after waiting a maximum of 5 seconds...
} catch (LockTimeoutException $e) {
    // Unable to acquire lock...
} finally {
    $lock->release();
}
```

The example above may be simplified by passing a closure to the `block` method. When a closure is passed to this method, Laravel will attempt to acquire the lock for the specified number of seconds and will automatically release the lock once the closure has been executed:

```
Cache::lock('foo', 10)->block(5, function () {
    // Lock acquired after waiting a maximum of 5 seconds...
});
```

#### [Managing Locks Across Processes](https://laravel.com/docs/11.x/cache#managing-locks-across-processes) <a href="#managing-locks-across-processes" id="managing-locks-across-processes"></a>

Sometimes, you may wish to acquire a lock in one process and release it in another process. For example, you may acquire a lock during a web request and wish to release the lock at the end of a queued job that is triggered by that request. In this scenario, you should pass the lock's scoped "owner token" to the queued job so that the job can re-instantiate the lock using the given token.

In the example below, we will dispatch a queued job if a lock is successfully acquired. In addition, we will pass the lock's owner token to the queued job via the lock's `owner` method:

```
$podcast = Podcast::find($id);
 
$lock = Cache::lock('processing', 120);
 
if ($lock->get()) {
    ProcessPodcast::dispatch($podcast, $lock->owner());
}
```

Within our application's `ProcessPodcast` job, we can restore and release the lock using the owner token:

```
Cache::restoreLock('processing', $this->owner)->release();
```

If you would like to release a lock without respecting its current owner, you may use the `forceRelease` method:

```
Cache::lock('processing')->forceRelease();
```

### [Events](https://laravel.com/docs/11.x/cache#events) <a href="#events" id="events"></a>

To execute code on every cache operation, you may listen for various [events](https://laravel.com/docs/11.x/events) dispatched by the cache:

| Event Name                             |
| -------------------------------------- |
| `Illuminate\Cache\Events\CacheHit`     |
| `Illuminate\Cache\Events\CacheMissed`  |
| `Illuminate\Cache\Events\KeyForgotten` |
| `Illuminate\Cache\Events\KeyWritten`   |
