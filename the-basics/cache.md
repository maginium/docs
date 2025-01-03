# 🗃️ Cache

* [Introduction](cache.md#introduction)
* [Configuration](cache.md#configuration)
  * [Driver Prerequisites](cache.md#driver-prerequisites)
* [Cache Usage](cache.md#cache-usage)
  * [Obtaining a Cache Instance](cache.md#obtaining-a-cache-instance)
  * [Retrieving Items From the Cache](cache.md#retrieving-items-from-the-cache)
  * [Storing Items in the Cache](cache.md#storing-items-in-the-cache)
  * [Removing Items From the Cache](cache.md#removing-items-from-the-cache)
  * [The Cache Helper](cache.md#the-cache-helper)
* [Atomic Locks](cache.md#atomic-locks)
  * [Managing Locks](cache.md#managing-locks)
  * [Managing Locks Across Processes](cache.md#managing-locks-across-processes)
* [Adding Custom Cache Drivers](cache.md#adding-custom-cache-drivers)
  * [Writing the Driver](cache.md#writing-the-driver)
  * [Registering the Driver](cache.md#registering-the-driver)
* [Events](cache.md#events)

## [Introduction](cache.md#introduction)

Some of the data retrieval or processing tasks performed by your application could be CPU intensive or take several seconds to complete. When this is the case, it is common to cache the retrieved data for a time so it can be retrieved quickly on subsequent requests for the same data. The cached data is usually stored in a very fast data store such as [Memcached](https://memcached.org) or [Redis](https://redis.io).

Thankfully, Maginium provides an expressive, unified API for various cache backends, allowing you to take advantage of their blazing fast data retrieval and speed up your web application.

## [Configuration](cache.md#configuration)

Your application's cache configuration file is located at `app/etc/env.php`. In this file, you may specify which cache store you would like to be used by default throughout your application. Maginium supports popular caching backends like [Memcached](https://memcached.org/), [Redis](https://redis.io/), [DynamoDB](https://aws.amazon.com/dynamodb), and relational databases out of the box. In addition, a file-based cache driver is available, while `array` and "null" cache drivers provide convenient cache backends for your automated tests.

The cache configuration file also contains a variety of other options that you may review. By default, Maginium is configured to use the `redis` cache driver, which stores the serialized, cached objects in your redis's instance.

#### [Driver Prerequisites](cache.md#driver-prerequisites) <a href="#driver-prerequisites" id="driver-prerequisites"></a>

[**Memcached**](cache.md#memcached)

Using the Memcached driver requires the [Memcached PECL package](https://pecl.php.net/package/memcached) to be installed. You may list all of your Memcached servers in the `app/etc/env.php` configuration file. This file already contains a `memcached.servers` entry to get you started:

```shell
MEMCACHED_HOST='/var/run/memcached/memcached.sock' || '127.0.0.1'
MEMCACHED_PORT= 0 || 11211
#MEMCACHED_WEIGHT=100
```

#### [Redis](cache.md#redis)

Before using a Redis cache with Maginium, you will need to either install the PhpRedis PHP extension via PECL or install the `predis/predis` package (\~2.0) via Composer. [Maginium Sail](../docs/%7B%7Bversion%7D%7D/sail/) already includes this extension. In addition, official Maginium deployment platforms such as [Maginium Forge](https://forge.maginium.com) and [Maginium Vapor](https://vapor.maginium.com) have the PhpRedis extension installed by default.

For more information on configuring Redis, consult its [Maginium documentation page](../docs/%7B%7Bversion%7D%7D/redis/#configuration).

#### [DynamoDB](cache.md#dynamodb)

Before using the [DynamoDB](https://aws.amazon.com/dynamodb) cache driver, you must create a DynamoDB table to store all of the cached data. Typically, this table should be named `cache`. However, you should name the table based on the value of the `stores.dynamodb.table` configuration value within the `cache` configuration file. The table name may also be set via the `DYNAMODB_CACHE_TABLE` environment variable.

This table should also have a string partition key with a name that corresponds to the value of the `stores.dynamodb.attributes.key` configuration item within your application's `cache` configuration file. By default, the partition key should be named `key`.

Typically, DynamoDB will not proactively remove expired items from a table. Therefore, you should [enable Time to Live (TTL)](https://docs.aws.amazon.com/amazondynamodb/latest/developerguide/TTL.html) on the table. When configuring the table's TTL settings, you should set the TTL attribute name to `expires_at`.

Next, install the AWS SDK so that your Maginium application can communicate with DynamoDB:

```shell
composer require aws/aws-sdk-php
```

In addition, you should ensure that values are provided for the DynamoDB cache store configuration options. Typically these options, such as `AWS_ACCESS_KEY_ID` and `AWS_SECRET_ACCESS_KEY`, should be defined in your application's `.env` configuration file:

```shell
# AWS Creds.
AWS_ACCESS_KEY_ID=
AWS_SECRET_ACCESS_KEY=
AWS_DEFAULT_REGION=us-east-1

# DynamoDB Configs.
DYNAMODB_CACHE_TABLE=cache
DYNAMODB_ENDPOINT=
```

#### [MongoDB](cache.md#mongodb)

If you are using MongoDB, a `mongodb` cache driver is provided by the official `mongodb/maginium-mongodb` package and can be configured using a `mongodb` database connection. MongoDB supports TTL indexes, which can be used to automatically clear expired cache items.

For more information on configuring MongoDB, please refer to the MongoDB [Cache and Locks documentation](https://www.mongodb.com/docs/drivers/php/maginium-mongodb/current/cache/).

## [Cache Usage](cache.md#cache-usage)

#### [Obtaining a Cache Instance](cache.md#obtaining-a-cache-instance)

To obtain a cache store instance, you may use the `Cache` facade, which is what we will use throughout this documentation. The `Cache` facade provides convenient, terse access to the underlying implementations of the Maginium cache contracts:

```php
<?php

namespace App\Http\Controllers;

use Maginium\Framework\Support\Collections\Facades\Cache;

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

#### [Accessing Multiple Cache Stores](cache.md#accessing-multiple-cache-stores)

Using the `Cache` facade, you may access various cache stores via the `store` method. The key passed to the `store` method should correspond to one of the stores listed in the `stores` configuration array in your `cache` configuration file:

```php
$value = Cache::store('file')->get('foo');

Cache::store('redis')->put('bar', 'baz', 600); // 10 Minutes
```

#### [Retrieving Items From the Cache](cache.md#retrieving-items-from-the-cache)

The `Cache` facade's `get` method is used to retrieve items from the cache. If the item does not exist in the cache, `null` will be returned. If you wish, you may pass a second argument to the `get` method specifying the default value you wish to be returned if the item doesn't exist:

```php
$value = Cache::get('key');

$value = Cache::get('key', 'default');
```

You may even pass a closure as the default value. The result of the closure will be returned if the specified item does not exist in the cache. Passing a closure allows you to defer the retrieval of default values from a database or other external service:

```php
$value = Cache::get('key', function () {
    return DB::table(/* ... */)->get();
});
```

#### [Determining Item Existence](cache.md#determining-item-existence)

The `has` method may be used to determine if an item exists in the cache. This method will also return `false` if the item exists but its value is `null`:

```php
if (Cache::has('key')) {
    // ...
}
```

#### [Incrementing / Decrementing Values](cache.md#incrementing-decrementing-values)

The `increment` and `decrement` methods may be used to adjust the value of integer items in the cache. Both of these methods accept an optional second argument indicating the amount by which to increment or decrement the item's value:

```php
// Initialize the value if it does not exist...
Cache::add('key', 0, now()->addHours(4));

// Increment or decrement the value...
Cache::increment('key');
Cache::increment('key', $amount);
Cache::decrement('key');
Cache::decrement('key', $amount);
```

#### [Retrieve and Store](cache.md#retrieve-store)

Sometimes you may wish to retrieve an item from the cache, but also store a default value if the requested item doesn't exist. For example, you may wish to retrieve all users from the cache or, if they don't exist, retrieve them from the database and add them to the cache. You may do this using the `Cache::remember` method:

```php
$value = Cache::remember('users', $seconds, function () {
    return DB::table('users')->get();
});
```

If the item does not exist in the cache, the closure passed to the `remember` method will be executed and its result will be placed in the cache.

You may use the `rememberForever` method to retrieve an item from the cache or store it forever if it does not exist:

```php
$value = Cache::rememberForever('users', function () {
    return DB::table('users')->get();
});
```

#### [Stale While Revalidate](cache.md#swr)

When using the `Cache::remember` method, some users may experience slow response times if the cached value has expired. For certain types of data, it can be useful to allow partially stale data to be served while the cached value is recalculated in the background, preventing some users from experiencing slow response times while cached values are calculated. This is often referred to as the "stale-while-revalidate" pattern, and the `Cache::flexible` method provides an implementation of this pattern.

The flexible method accepts an array that specifies how long the cached value is considered “fresh” and when it becomes “stale.” The first value in the array represents the number of seconds the cache is considered fresh, while the second value defines how long it can be served as stale data before recalculation is necessary.

If a request is made within the fresh period (before the first value), the cache is returned immediately without recalculation. If a request is made during the stale period (between the two values), the stale value is served to the user, and a [deferred function](../docs/%7B%7Bversion%7D%7D/helpers/#deferred-functions) is registered to refresh the cached value after the response is sent to the user. If a request is made after the second value, the cache is considered expired, and the value is recalculated immediately, which may result in a slower response for the user:

```php
$value = Cache::flexible('users', [5, 10], function () {
    return DB::table('users')->get();
});
```

#### [Retrieve and Delete](cache.md#retrieve-delete)

If you need to retrieve an item from the cache and then delete the item, you may use the `pull` method. Like the `get` method, `null` will be returned if the item does not exist in the cache:

```php
$value = Cache::pull('key');

$value = Cache::pull('key', 'default');
```

#### [Storing Items in the Cache](cache.md#storing-items-in-the-cache)

You may use the `put` method on the `Cache` facade to store items in the cache:

```php
Cache::put('key', 'value', $seconds = 10);
```

If the storage time is not passed to the `put` method, the item will be stored indefinitely:

```php
Cache::put('key', 'value');
```

Instead of passing the number of seconds as an integer, you may also pass a `DateTime` instance representing the desired expiration time of the cached item:

```php
Cache::put('key', 'value', now()->addMinutes(10));
```

#### [Store if Not Present](cache.md#store-if-not-present)

The `add` method will only add the item to the cache if it does not already exist in the cache store. The method will return `true` if the item is actually added to the cache. Otherwise, the method will return `false`. The `add` method is an atomic operation:

```php
Cache::add('key', 'value', $seconds);
```

#### [Storing Items Forever](cache.md#storing-items-forever)

The `forever` method may be used to store an item in the cache permanently. Since these items will not expire, they must be manually removed from the cache using the `forget` method:

```php
Cache::forever('key', 'value');
```

{% hint style="info" %}
If you are using the Memcached driver, items that are stored "forever" may be removed when the cache reaches its size limit.
{% endhint %}

#### [Removing Items From the Cache](cache.md#removing-items-from-the-cache)

You may remove items from the cache using the `forget` method:

```php
Cache::forget('key');
```

You may also remove items by providing a zero or negative number of expiration seconds:

```php
Cache::put('key', 'value', 0);

Cache::put('key', 'value', -5);
```

You may clear the entire cache using the `flush` method:

```php
Cache::flush();
```

{% hint style="warning" %}
Flushing the cache does not respect your configured cache "prefix" and will remove all entries from the cache. Consider this carefully when clearing a cache which is shared by other applications.
{% endhint %}

#### [The Cache Helper](cache.md#the-cache-helper)

In addition to using the `Cache` facade, you may also use the global `cache` function to retrieve and store data via the cache. When the `cache` function is called with a single, string argument, it will return the value of the given key:

```php
$value = cache('key');
```

If you provide an array of key / value pairs and an expiration time to the function, it will store values in the cache for the specified duration:

```php
Cache(['key' => 'value'], $seconds);

cache(['key' => 'value'], now()->addMinutes(10));
```

When the `cache` function is called without any arguments, it returns an instance of the `Illuminate\Contracts\Cache\Factory` implementation, allowing you to call other caching methods:

```php
Cache()->remember('users', $seconds, function () {
    return DB::table('users')->get();
});
```

{% hint style="info" %}
When testing calls to the global `cache` function, you may use the `Cache::shouldReceive` method just as if you were [testing the facade](../docs/%7B%7Bversion%7D%7D/mocking/#mocking-facades).
{% endhint %}

## [Atomic Locks](cache.md#atomic-locks)

{% hint style="warning" %}
To utilize this feature, your application must be using the `memcached`, `redis`, `dynamodb`, `file`, or `array` cache driver as your application's default cache driver. In addition, all servers must be communicating with the same central cache server.
{% endhint %}

#### [Managing Locks](cache.md#managing-locks)

Atomic locks allow for the manipulation of distributed locks without worrying about race conditions. For example, [Maginium Forge](https://forge.maginium.com) uses atomic locks to ensure that only one remote task is being executed on a server at a time. You may create and manage locks using the `Cache::lock` method:

```
use Maginium\Framework\Support\Collections\Facades\Cache;

$lock = Cache::lock('foo', 10);

if ($lock->get()) {
    // Lock acquired for 10 seconds...

    $lock->release();
}
```

The `get` method also accepts a closure. After the closure is executed, Maginium will automatically release the lock:

```php
Cache::lock('foo', 10)->get(function () {
    // Lock acquired for 10 seconds and automatically released...
});
```

If the lock is not available at the moment you request it, you may instruct Maginium to wait for a specified number of seconds. If the lock cannot be acquired within the specified time limit, an `Illuminate\Contracts\Cache\LockTimeoutException` will be thrown:

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

The example above may be simplified by passing a closure to the `block` method. When a closure is passed to this method, Maginium will attempt to acquire the lock for the specified number of seconds and will automatically release the lock once the closure has been executed:

```php
Cache::lock('foo', 10)->block(5, function () {
    // Lock acquired after waiting a maximum of 5 seconds...
});
```

#### [Managing Locks Across Processes](cache.md#managing-locks-across-processes)

Sometimes, you may wish to acquire a lock in one process and release it in another process. For example, you may acquire a lock during a web request and wish to release the lock at the end of a queued job that is triggered by that request. In this scenario, you should pass the lock's scoped "owner token" to the queued job so that the job can re-instantiate the lock using the given token.

In the example below, we will dispatch a queued job if a lock is successfully acquired. In addition, we will pass the lock's owner token to the queued job via the lock's `owner` method:

```php
$podcast = Podcast::find($id);

$lock = Cache::lock('processing', 120);

if ($lock->get()) {
    ProcessPodcast::dispatch($podcast, $lock->owner());
}
```

Within our application's `ProcessPodcast` job, we can restore and release the lock using the owner token:

```php
Cache::restoreLock('processing', $this->owner)->release();
```

If you would like to release a lock without respecting its current owner, you may use the `forceRelease` method:

```php
Cache::lock('processing')->forceRelease();
```

## [Events](cache.md#events)

To execute code on every cache operation, you may listen for various [events](../docs/%7B%7Bversion%7D%7D/events/) dispatched by the cache:

| Event Name                                                 |
| ---------------------------------------------------------- |
| `Maginium\Framework\Cache\Collections\Events\CacheHit`     |
| `Maginium\Framework\Cache\Collections\Events\CacheMissed`  |
| `Maginium\Framework\Cache\Collections\Events\KeyForgotten` |
| `Maginium\Framework\Cache\Collections\Events\KeyWritten`   |
