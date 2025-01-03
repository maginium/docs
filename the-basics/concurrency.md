---
icon: gear-code
---

# Concurrency

* [Introduction](concurrency.md#introduction)
* [Running Concurrent Tasks](concurrency.md#running-concurrent-tasks)
* [Deferring Concurrent Tasks](concurrency.md#deferring-concurrent-tasks)

### [Introduction](concurrency.md#introduction) <a href="#introduction" id="introduction"></a>

{% hint style="warning" %}
Maginium's `Concurrency` facade is currently in beta while we gather community feedback.
{% endhint %}

Sometimes you may need to execute several slow tasks that do not depend on one another. In many cases, significant performance improvements can be realized by executing the tasks concurrently. Maginium's `Concurrency` facade provides a simple, convenient API for executing closures concurrently.

<a name="concurrency-compatibility" href="#concurrency-compatibility" id="concurrency-compatibility"></a>
[**Concurrency Compatibility**](concurrency.md#concurrency-compatibility)

Maginium extends the `Illuminate\Concurrency` classes to make it compatible with Maginium, a framework built on top of Magento 2. This integration enables Magento applications to leverage concurrency for better task execution.

<a name="how-it-works" href="#how-it-works" id="how-it-works"></a>
[**How it Works**](concurrency.md#how-it-works)

Maginium achieves concurrency by serializing the given closures and dispatching them to a hidden Artisan CLI command. This command unserializes the closures and invokes them within its PHP process. After the closure has been invoked, the resulting value is serialized back to the parent process.

The `Concurrency` facade supports three drivers: `process` (the default), `fork`, and `sync`.

The `fork` driver offers improved performance compared to the default `process` driver, but it may only be used within PHP's CLI context, as PHP does not support forking during web requests. Before using the `fork` driver, you need to install the `spatie/fork` package:

```shell
composer require spatie/fork
```

The `sync` driver is primarily useful during testing when you want to disable all concurrency and execute the given closures in sequence within the parent process.

<a name="running-concurrent-tasks" href="#running-concurrent-tasks" id="running-concurrent-tasks"></a>

### [Running Concurrent Tasks](concurrency.md#running-concurrent-tasks)

To run concurrent tasks, you may invoke the `Concurrency` facade's `run` method. The `run` method accepts an array of closures that should be executed simultaneously in child PHP processes:

```php
use Maginium\Framework\Support\Facades\Concurrency;
use Maginium\Framework\Support\Facades\DB;

[$userCount, $orderCount] = Concurrency::run([
    fn () => DB::table('users')->count(),
    fn () => DB::table('orders')->count(),
]);
```

To use a specific driver, you may use the `driver` method:

```php
$results = Concurrency::driver('fork')->run(...);
```

Or, to change the default concurrency driver, you can set the corresponding environment variable. Update the .env file with the following:

```shell
CONCURRENCY_DRIVER=fork
```

<a name="deferring-concurrent-tasks" href="#deferring-concurrent-tasks" id="deferring-concurrent-tasks"></a>

### [Deferring Concurrent Tasks](concurrency.md#deferring-concurrent-tasks)

If you would like to execute an array of closures concurrently but are not interested in the results returned by those closures, you should consider using the `defer` method. When the `defer` method is invoked, the given closures are not executed immediately. Instead, Maginium will execute the closures concurrently after the HTTP response has been sent to the user:

```php
use App\Services\Metrics;
use Maginium\Framework\Support\Facades\Concurrency;
 
Concurrency::defer([
    fn () => Metrics::report('users'),
    fn () => Metrics::report('orders'),
]);
```
