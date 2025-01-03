# 👤 Avatar

* ​[Introduction](https://app.gitbook.com/o/-MPhpm6jDv_mkGK-DS4c/s/QUqmoTAixbfwsdTXwL2O/the-basics/concurrency#introduction)​
* Usage

## Introduction

Display a unique avatar for any user based on their (initials) name.

{% hint style="warning" %}
This Module is inspired by [Laravolt](https://github.com/laravolt/avatar)
{% endhint %}

## Usage

### Output as base64

```php
//this will output data-uri (base64 image data)
//something like data:image/png;base64,iVBORw0KGg....
Avatar::create('Joko Widodo')->toBase64();

//use in view
//this will display initials JW as an image
<img src="{{ Avatar::create('Joko Widodo')->toBase64() }}" />
```

### Save as file

```php
Avatar::create('Susilo Bambang Yudhoyono')->save('sample.png');
Avatar::create('Susilo Bambang Yudhoyono')->save('sample.jpg', 100); // quality = 100
```

### Output as Gravatar

```php
Avatar::create('uyab@example.net')->toGravatar();
// Output: http://gravatar.com/avatar/0c5cbf5a8762d91d930795a6107b2ce5814a6ab26e60c7ec6b75bc81c7dfe3ee

Avatar::create('uyab@example.net')->toGravatar(['d' => 'identicon', 'r' => 'pg', 's' => 100]);
// Output: http://gravatar.com/avatar/0c5cbf5a8762d91d930795a6107b2ce5814a6ab26e60c7ec6b75bc81c7dfe3ee?d=identicon&r=pg&s=100
```

{% hint style="info" %}
Gravatar parameter [reference](https://docs.gravatar.com/api/avatars/images/)
{% endhint %}

### Output as SVG

```php
Avatar::create('Susilo Bambang Yudhoyono')->toSvg();
```

You may specify a custom font family for your SVG text.

```php
<head>
    <!--Prepare custom font family, using Google Fonts-->
    <link href="https://fonts.googleapis.com/css?family=inter" rel="stylesheet">

    <!--OR-->

    <!--Setup your own style-->
    <style>
    @font-face {
        font-family: Inter;
        src: url({{ asset('fonts/inter.woff')) }});
    }
    </style>
</head>
```

```php
Avatar::create('Susilo Bambang Yudhoyono')->setFontFamily('Inter')->toSvg();
```

### Get underlying Intervention image object

```php
Avatar::create('Abdul Somad')->getImageObject();
```

The method will return an instance of the [Intervention image object](http://image.intervention.io/), so you can use it for further purposes.

### Non-ASCII Character

By default, this package will try to output any initials letter as it is. If the name supplied contains any non-ASCII character (e.g. ā, Ě, ǽ) then the result will depend on which font is used (see config). It the font supports the characters supplied, it will be successfully displayed, otherwise it will not.

Alternatively, we can convert all non-ascii to their closest ASCII counterparts. If no closest counterparts are found, those characters are removed. Thanks to [Stringy](https://github.com/danielstjules/Stringy) for providing such useful functions.

### Overriding config at runtime

We can override configuration at runtime by using the following functions:

```php
Avatar::create('Soekarno')->setDimension(100);//width = height = 100 pixel
Avatar::create('Soekarno')->setDimension(100, 200); // width = 100, height = 200
Avatar::create('Soekarno')->setBackground('#001122');
Avatar::create('Soekarno')->setForeground('#999999');
Avatar::create('Soekarno')->setFontSize(72);
Avatar::create('Soekarno')->setFont('/path/to/font.ttf');
Avatar::create('Soekarno')->setBorder(1, '#aabbcc'); // size = 1, color = #aabbcc
Avatar::create('Soekarno')->setBorder(1, '#aabbcc', 10); // size = 1, color = #aabbcc, border radius = 10 (only for SVG)
Avatar::create('Soekarno')->setShape('square');

// Available since 3.0.0
Avatar::create('Soekarno')->setTheme('colorful'); // set exact theme
Avatar::create('Soekarno')->setTheme(['grayscale-light', 'grayscale-dark']); // theme will be randomized from these two options

// chaining
Avatar::create('Habibie')->setDimension(50)->setFontSize(18)->toBase64();
```
