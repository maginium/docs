# 👤 Avatar

Output as base64

```
//this will output data-uri (base64 image data)
//something like data:image/png;base64,iVBORw0KGg....
Avatar::create('Joko Widodo')->toBase64();

//use in view
//this will display initials JW as an image
<img src="{{ Avatar::create('Joko Widodo')->toBase64() }}" />
```

Save as file

```
Avatar::create('Susilo Bambang Yudhoyono')->save('sample.png');
Avatar::create('Susilo Bambang Yudhoyono')->save('sample.jpg', 100); // quality = 100
```

Output as Gravatar

```
Avatar::create('uyab@example.net')->toGravatar();
// Output: http://gravatar.com/avatar/0c5cbf5a8762d91d930795a6107b2ce5814a6ab26e60c7ec6b75bc81c7dfe3ee

Avatar::create('uyab@example.net')->toGravatar(['d' => 'identicon', 'r' => 'pg', 's' => 100]);
// Output: http://gravatar.com/avatar/0c5cbf5a8762d91d930795a6107b2ce5814a6ab26e60c7ec6b75bc81c7dfe3ee?d=identicon&r=pg&s=100
```

Gravatar parameter reference: [https://docs.gravatar.com/api/avatars/images/](https://docs.gravatar.com/api/avatars/images/)

Output as SVG

```
Avatar::create('Susilo Bambang Yudhoyono')->toSvg();
```

You may specify a custom font family for your SVG text.

```
<head>
    <!--Prepare custom font family, using Google Fonts-->
    <link href="https://fonts.googleapis.com/css?family=Laravolt" rel="stylesheet">

    <!--OR-->

    <!--Setup your own style-->
    <style>
    @font-face {
        font-family: Laravolt;
        src: url({{ asset('fonts/laravolt.woff')) }});
    }
    </style>
</head>
```

```
Avatar::create('Susilo Bambang Yudhoyono')->setFontFamily('Laravolt')->toSvg();
```

### Get underlying Intervention image object

```
Avatar::create('Abdul Somad')->getImageObject();
```

The method will return an instance of the [Intervention image object](http://image.intervention.io/), so you can use it for further purposes.

### Non-ASCII Character

By default, this package will try to output any initials letter as it is. If the name supplied contains any non-ASCII character (e.g. ā, Ě, ǽ) then the result will depend on which font is used (see config). It the font supports the characters supplied, it will be successfully displayed, otherwise it will not.

Alternatively, we can convert all non-ascii to their closest ASCII counterparts. If no closest counterparts are found, those characters are removed. Thanks to [Stringy](https://github.com/danielstjules/Stringy) for providing such useful functions. What we need is just to change one line in `config/avatar.php`:

```
    'ascii'    => true,
```
