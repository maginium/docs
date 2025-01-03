# 👤 Avatar

* [Introduction](avatar.md#introduction)
* [Usage](avatar.md#usage)

<a name="introduction" href="#introduction" id="introduction"></a>

## [Introduction](avatar.md#introduction)

Display a unique avatar for any user based on their (initials) name.

{% hint style="warning" %}
This Module is inspired by [Laravolt](https://github.com/laravolt/avatar)
{% endhint %}

<a name="usage" href="#usage" id="usage"></a>

## [Usage](avatar.md#usage)

<a name="output-as-base64" href="#output-as-base64" id="output-as-base64"></a>
#### [Output as Base64](avatar.md#output-as-base64)

```php
// This will output data-uri (base64 image data), e.g., data:image/png;base64,iVBORw0KGg...
Avatar::create('Joko Widodo')->toBase64();

// Use in view to display initials as an image
<img src="{{ Avatar::create('Joko Widodo')->toBase64() }}" />
```

<a name="save-as-file" href="#save-as-file" id="save-as-file"></a>

#### [Save as File](avatar.md#save-as-file)

```php
Avatar::create('Susilo Bambang Yudhoyono')->save('sample.png');
Avatar::create('Susilo Bambang Yudhoyono')->save('sample.jpg', 100); // Quality = 100
```

<a name="output-as-gravatar" href="#output-as-gravatar" id="output-as-gravatar"></a>

#### [Output as Gravatar](avatar.md#output-as-gravatar)

```php
Avatar::create('uyab@example.net')->toGravatar();
// Output: http://gravatar.com/avatar/...

Avatar::create('uyab@example.net')->toGravatar(['d' => 'identicon', 'r' => 'pg', 's' => 100]);
// Output: http://gravatar.com/avatar/...&d=identicon&r=pg&s=100
```

{% hint style="info” %}
Gravatar parameter reference
{% endhint %}

<a name="output-as-svg" href="#output-as-svg" id="output-as-svg"></a>

#### [Output as SVG](avatar.md#output-as-svg)

```php
Avatar::create('Susilo Bambang Yudhoyono')->toSvg();
```

You may specify a custom font family for your SVG text.

```php
<head>
    <!-- Using Google Fonts -->
    <link href="https://fonts.googleapis.com/css?family=Inter" rel="stylesheet">

    <!-- OR Setup custom style -->
    <style>
    @font-face {
        font-family: Inter;
        src: url({{ asset('fonts/inter.woff') }});
    }
    </style>
</head>
```

```php
Avatar::create('Susilo Bambang Yudhoyono')->setFontFamily('Inter')->toSvg();
```

<a name="get-underlying-intervention-image-object" href="#get-underlying-intervention-image-object" id="get-underlying-intervention-image-object"></a>

#### [Get Underlying Intervention Image Object](avatar.md#get-underlying-intervention-image-object)

```php
Avatar::create('Abdul Somad')->getImageObject();
```

Returns an instance of the Intervention image object, enabling further processing.

<a name="non-ascii-character" href="#non-ascii-character" id="non-ascii-character"></a>

#### [Non-ASCII Character](avatar.md#non-ascii-character)

The library tries to render initials as supplied. For non-ASCII characters (e.g., ā, Ě), their visibility depends on font support. Alternatively, non-ASCII characters can be converted to their closest ASCII counterparts using Stringy.

<a name="override-config-at-runtime" href="#override-config-at-runtime" id="override-config-at-runtime"></a>

#### [Overriding Config at Runtime](avatar.md#override-config-at-runtime)

```php
Avatar::create('Soekarno')->setDimension(100); // Width = Height = 100 pixels
Avatar::create('Soekarno')->setDimension(100, 200); // Width = 100, Height = 200
Avatar::create('Soekarno')->setBackground('#001122');
Avatar::create('Soekarno')->setForeground('#999999');
Avatar::create('Soekarno')->setFontSize(72);
Avatar::create('Soekarno')->setFont('/path/to/font.ttf');
Avatar::create('Soekarno')->setBorder(1, '#aabbcc'); // Size = 1, Color = #aabbcc
Avatar::create('Soekarno')->setBorder(1, '#aabbcc', 10); // Border radius = 10 (for SVG only)
Avatar::create('Soekarno')->setShape('square');

// Since v3.0.0
Avatar::create('Soekarno')->setTheme('colorful'); // Set exact theme
Avatar::create('Soekarno')->setTheme(['grayscale-light', 'grayscale-dark']); // Random theme from options

// Chaining
Avatar::create('Habibie')->setDimension(50)->setFontSize(18)->toBase64();
```
