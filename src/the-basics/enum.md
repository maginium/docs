# 🔠 Enum

Maginium introduces support for Enums, offering a clean and robust way to manage a predefined set of constants within your application. Enums are
particularly useful for handling fixed values, like user roles, order statuses, or other categorical data. By leveraging Enums, you can improve code
readability, reduce errors, and standardize the handling of constant data.

---

### What are Enums?

Enums (short for Enumerations) are a special type of data structure that allows you to define a set of named constants. In Maginium, Enums are
implemented as PHP backed Enums, providing both functionality and type safety.

For example, consider an Enum representing the roles in an application:

```php
<?php

enum UserRole: string
{
    case ADMIN = 'admin';
    case EDITOR = 'editor';
    case VIEWER = 'viewer';
}
```

With the `UserRole` Enum, you can easily reference roles in a type-safe manner:

```php
$userRole = UserRole::ADMIN;
if ($userRole === UserRole::EDITOR) {
    echo 'User is an editor';
}
```

---

### Defining Enums in Maginium

To define an Enum in Maginium, use the `enum` keyword followed by the Enum name and type. Enums can be backed by `string` or `int` values to associate
constants with scalar data.

\### Example: Order Status Enum

```php
<?php

enum OrderStatus: string
{
    case PENDING = 'pending';
    case COMPLETED = 'completed';
    case CANCELLED = 'cancelled';
}
```

You can then use this Enum to manage order statuses consistently throughout your application:

```php
$orderStatus = OrderStatus::PENDING;

if ($orderStatus === OrderStatus::COMPLETED) {
    echo 'Order is completed';
}
```

> **Important**: Enums provide a centralized source of truth for fixed constants, minimizing the risk of typos and logical errors.

---

### Enum Methods

Enums in Maginium allow you to define methods within the Enum class to encapsulate logic specific to the Enum.

\### Example: User Role Permissions

```php
<?php

enum UserRole: string
{
    case ADMIN = 'admin';
    case EDITOR = 'editor';
    case VIEWER = 'viewer';

    public function hasPermission(string $action): bool
    {
        return match ($this) {
            self::ADMIN => true,
            self::EDITOR => in_array($action, ['edit', 'view']),
            self::VIEWER => $action === 'view',
        };
    }
}
```

Using this method:

```php
$role = UserRole::EDITOR;

if ($role->hasPermission('edit')) {
    echo 'Editor can edit';
}
```

{% hint style="info" %} Adding methods to Enums promotes reusability and keeps related logic encapsulated within the Enum itself. {% endhint %}

---

### Enum Reflection

Maginium provides utility methods to work with Enums, including listing cases or retrieving values.

\### Listing Enum Cases

```php
$cases = OrderStatus::cases();
foreach ($cases as $case) {
    echo $case->name . ' (' . $case->value . ')';
}
// Outputs:
// PENDING (pending)
// COMPLETED (completed)
// CANCELLED (cancelled)
```

\### Validating Enum Values

```php
$isValid = in_array('completed', array_column(OrderStatus::cases(), 'value'));
if ($isValid) {
    echo 'Valid status';
}
```

> **Tip**: Use reflection utilities to dynamically work with Enum cases and values without hardcoding logic.

---

### Enums in Database

When using Enums in database operations, you can store the Enum values directly. Maginium simplifies this by seamlessly integrating Enums into
Eloquent models.

\### Example: Enum in Eloquent Models

```php
<?php

use Maginium\Framework\Database\Model;
use Maginium\Framework\Support\Casts\EnumCast;

class Order extends Model
{
    protected $casts = [
        'status' => EnumCast::class . ':' . OrderStatus::class,
    ];
}
```

With this setup, the `status` field in the `Order` model will automatically be cast to and from the `OrderStatus` Enum.

---

---
