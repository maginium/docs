# 🔤 Strings

* [Introduction](strings.md#introduction)
* [Available Methods](strings.md#available-methods)

### [Introduction](strings.md#introduction) <a href="#introduction" id="introduction"></a>

Laravel includes a variety of functions for manipulating string values. Many of these functions are used by the framework itself; however, you are free to use them in your own applications if you find them convenient.

### [Available Methods](strings.md#available-methods) <a href="#available-methods" id="available-methods"></a>

#### [Strings](strings.md#strings-method-list) <a href="#strings-method-list" id="strings-method-list"></a>

| [\_\_](strings.md#method-__)                                 | [class\_basename](strings.md#method-class-basename)    | [e](strings.md#method-e)                                     |
| ------------------------------------------------------------ | ------------------------------------------------------ | ------------------------------------------------------------ |
| [preg\_replace\_array](strings.md#method-preg-replace-array) | [Str::after](strings.md#method-str-after)              | [Str::afterLast](strings.md#method-str-after-last)           |
| [Str::apa](strings.md#method-str-apa)                        | [Str::ascii](strings.md#method-str-ascii)              | [Str::before](strings.md#method-str-before)                  |
| [Str::beforeLast](strings.md#method-str-before-last)         | [Str::between](strings.md#method-str-between)          | [Str::betweenFirst](strings.md#method-str-between-first)     |
| [Str::camel](strings.md#method-camel-case)                   | [Str::charAt](strings.md#method-char-at)               | [Str::chopStart](strings.md#method-str-chop-start)           |
| [Str::chopEnd](strings.md#method-str-chop-end)               | [Str::contains](strings.md#method-str-contains)        | [Str::containsAll](strings.md#method-str-contains-all)       |
| [Str::doesntContain](strings.md#method-str-doesnt-contain)   | [Str::deduplicate](strings.md#method-deduplicate)      | [Str::endsWith](strings.md#method-ends-with)                 |
| [Str::excerpt](strings.md#method-excerpt)                    | [Str::finish](strings.md#method-str-finish)            | [Str::headline](strings.md#method-str-headline)              |
| [Str::inlineMarkdown](strings.md#method-str-inline-markdown) | [Str::is](strings.md#method-str-is)                    | [Str::isAscii](strings.md#method-str-is-ascii)               |
| [Str::isJson](strings.md#method-str-is-json)                 | [Str::isUlid](strings.md#method-str-is-ulid)           | [Str::isUrl](strings.md#method-str-is-url)                   |
| [Str::isUuid](strings.md#method-str-is-uuid)                 | [Str::kebab](strings.md#method-kebab-case)             | [Str::lcfirst](strings.md#method-str-lcfirst)                |
| [Str::length](strings.md#method-str-length)                  | [Str::limit](strings.md#method-str-limit)              | [Str::lower](strings.md#method-str-lower)                    |
| [Str::markdown](strings.md#method-str-markdown)              | [Str::mask](strings.md#method-str-mask)                | [Str::orderedUuid](strings.md#method-str-ordered-uuid)       |
| [Str::padBoth](strings.md#method-str-padboth)                | [Str::padLeft](strings.md#method-str-padleft)          | [Str::padRight](strings.md#method-str-padright)              |
| [Str::password](strings.md#method-str-password)              | [Str::plural](strings.md#method-str-plural)            | [Str::pluralStudly](strings.md#method-str-plural-studly)     |
| [Str::position](strings.md#method-str-position)              | [Str::random](strings.md#method-str-random)            | [Str::remove](strings.md#method-str-remove)                  |
| [Str::repeat](strings.md#method-str-repeat)                  | [Str::replace](strings.md#method-str-replace)          | [Str::replaceArray](strings.md#method-str-replace-array)     |
| [Str::replaceFirst](strings.md#method-str-replace-first)     | [Str::replaceLast](strings.md#method-str-replace-last) | [Str::replaceMatches](strings.md#method-str-replace-matches) |
| [Str::replaceStart](strings.md#method-str-replace-start)     | [Str::replaceEnd](strings.md#method-str-replace-end)   | [Str::reverse](strings.md#method-str-reverse)                |
| [Str::singular](strings.md#method-str-singular)              | [Str::slug](strings.md#method-str-slug)                | [Str::snake](strings.md#method-snake-case)                   |
| [Str::squish](strings.md#method-str-squish)                  | [Str::start](strings.md#method-str-start)              | [Str::startsWith](strings.md#method-starts-with)             |
| [Str::studly](strings.md#method-studly-case)                 | [Str::substr](strings.md#method-str-substr)            | [Str::substrCount](strings.md#method-str-substrcount)        |
| [Str::substrReplace](strings.md#method-str-substrreplace)    | [Str::swap](strings.md#method-str-swap)                | [Str::take](strings.md#method-take)                          |
| [Str::title](strings.md#method-title-case)                   | [Str::toBase64](strings.md#method-str-to-base64)       | [Str::transliterate](strings.md#method-str-transliterate)    |
| [Str::trim](strings.md#method-str-trim)                      | [Str::ltrim](strings.md#method-str-ltrim)              | [Str::rtrim](strings.md#method-str-rtrim)                    |
| [Str::ucfirst](strings.md#method-str-ucfirst)                | [Str::ucsplit](strings.md#method-str-ucsplit)          | [Str::upper](strings.md#method-str-upper)                    |
| [Str::ulid](strings.md#method-str-ulid)                      | [Str::unwrap](strings.md#method-str-unwrap)            | [Str::uuid](strings.md#method-str-uuid)                      |
| [Str::wordCount](strings.md#method-str-word-count)           | [Str::wordWrap](strings.md#method-str-word-wrap)       | [Str::words](strings.md#method-str-words)                    |
| [Str::wrap](strings.md#method-str-wrap)                      | [str](strings.md#method-str)                           | [trans](strings.md#method-trans)                             |
| [trans\_choice](strings.md#method-trans-choice)              |                                                        |                                                              |

#### [Fluent Strings](strings.md#fluent-strings-method-list) <a href="#fluent-strings-method-list" id="fluent-strings-method-list"></a>

| [after](strings.md#method-fluent-str-after)                       | [afterLast](strings.md#method-fluent-str-after-last)           | [apa](strings.md#method-fluent-str-apa)                     |
| ----------------------------------------------------------------- | -------------------------------------------------------------- | ----------------------------------------------------------- |
| [append](strings.md#method-fluent-str-append)                     | [ascii](strings.md#method-fluent-str-ascii)                    | [basename](strings.md#method-fluent-str-basename)           |
| [before](strings.md#method-fluent-str-before)                     | [beforeLast](strings.md#method-fluent-str-before-last)         | [between](strings.md#method-fluent-str-between)             |
| [betweenFirst](strings.md#method-fluent-str-between-first)        | [camel](strings.md#method-fluent-str-camel)                    | [charAt](strings.md#method-fluent-str-char-at)              |
| [classBasename](strings.md#method-fluent-str-class-basename)      | [chopStart](strings.md#method-fluent-str-chop-start)           | [chopEnd](strings.md#method-fluent-str-chop-end)            |
| [contains](strings.md#method-fluent-str-contains)                 | [containsAll](strings.md#method-fluent-str-contains-all)       | [deduplicate](strings.md#method-fluent-str-deduplicate)     |
| [dirname](strings.md#method-fluent-str-dirname)                   | [endsWith](strings.md#method-fluent-str-ends-with)             | [exactly](strings.md#method-fluent-str-exactly)             |
| [excerpt](strings.md#method-fluent-str-excerpt)                   | [explode](strings.md#method-fluent-str-explode)                | [finish](strings.md#method-fluent-str-finish)               |
| [headline](strings.md#method-fluent-str-headline)                 | [inlineMarkdown](strings.md#method-fluent-str-inline-markdown) | [is](strings.md#method-fluent-str-is)                       |
| [isAscii](strings.md#method-fluent-str-is-ascii)                  | [isEmpty](strings.md#method-fluent-str-is-empty)               | [isNotEmpty](strings.md#method-fluent-str-is-not-empty)     |
| [isJson](strings.md#method-fluent-str-is-json)                    | [isUlid](strings.md#method-fluent-str-is-ulid)                 | [isUrl](strings.md#method-fluent-str-is-url)                |
| [isUuid](strings.md#method-fluent-str-is-uuid)                    | [kebab](strings.md#method-fluent-str-kebab)                    | [lcfirst](strings.md#method-fluent-str-lcfirst)             |
| [length](strings.md#method-fluent-str-length)                     | [limit](strings.md#method-fluent-str-limit)                    | [lower](strings.md#method-fluent-str-lower)                 |
| [markdown](strings.md#method-fluent-str-markdown)                 | [mask](strings.md#method-fluent-str-mask)                      | [match](strings.md#method-fluent-str-match)                 |
| [matchAll](strings.md#method-fluent-str-match-all)                | [isMatch](strings.md#method-fluent-str-is-match)               | [newLine](strings.md#method-fluent-str-new-line)            |
| [padBoth](strings.md#method-fluent-str-padboth)                   | [padLeft](strings.md#method-fluent-str-padleft)                | [padRight](strings.md#method-fluent-str-padright)           |
| [pipe](strings.md#method-fluent-str-pipe)                         | [plural](strings.md#method-fluent-str-plural)                  | [position](strings.md#method-fluent-str-position)           |
| [prepend](strings.md#method-fluent-str-prepend)                   | [remove](strings.md#method-fluent-str-remove)                  | [repeat](strings.md#method-fluent-str-repeat)               |
| [replace](strings.md#method-fluent-str-replace)                   | [replaceArray](strings.md#method-fluent-str-replace-array)     | [replaceFirst](strings.md#method-fluent-str-replace-first)  |
| [replaceLast](strings.md#method-fluent-str-replace-last)          | [replaceMatches](strings.md#method-fluent-str-replace-matches) | [replaceStart](strings.md#method-fluent-str-replace-start)  |
| [replaceEnd](strings.md#method-fluent-str-replace-end)            | [scan](strings.md#method-fluent-str-scan)                      | [singular](strings.md#method-fluent-str-singular)           |
| [slug](strings.md#method-fluent-str-slug)                         | [snake](strings.md#method-fluent-str-snake)                    | [split](strings.md#method-fluent-str-split)                 |
| [squish](strings.md#method-fluent-str-squish)                     | [start](strings.md#method-fluent-str-start)                    | [startsWith](strings.md#method-fluent-str-starts-with)      |
| [stripTags](strings.md#method-fluent-str-strip-tags)              | [studly](strings.md#method-fluent-str-studly)                  | [substr](strings.md#method-fluent-str-substr)               |
| [substrReplace](strings.md#method-fluent-str-substrreplace)       | [swap](strings.md#method-fluent-str-swap)                      | [take](strings.md#method-fluent-str-take)                   |
| [tap](strings.md#method-fluent-str-tap)                           | [test](strings.md#method-fluent-str-test)                      | [title](strings.md#method-fluent-str-title)                 |
| [toBase64](strings.md#method-fluent-str-to-base64)                | [toHtmlString](strings.md#method-fluent-str-to-html-string)    | [transliterate](strings.md#method-fluent-str-transliterate) |
| [trim](strings.md#method-fluent-str-trim)                         | [ltrim](strings.md#method-fluent-str-ltrim)                    | [rtrim](strings.md#method-fluent-str-rtrim)                 |
| [ucfirst](strings.md#method-fluent-str-ucfirst)                   | [ucsplit](strings.md#method-fluent-str-ucsplit)                | [unwrap](strings.md#method-fluent-str-unwrap)               |
| [upper](strings.md#method-fluent-str-upper)                       | [when](strings.md#method-fluent-str-when)                      | [whenContains](strings.md#method-fluent-str-when-contains)  |
| [whenContainsAll](strings.md#method-fluent-str-when-contains-all) | [whenEmpty](strings.md#method-fluent-str-when-empty)           | [whenNotEmpty](strings.md#method-fluent-str-when-not-empty) |
| [whenStartsWith](strings.md#method-fluent-str-when-starts-with)   | [whenEndsWith](strings.md#method-fluent-str-when-ends-with)    | [whenExactly](strings.md#method-fluent-str-when-exactly)    |
| [whenNotExactly](strings.md#method-fluent-str-when-not-exactly)   | [whenIs](strings.md#method-fluent-str-when-is)                 | [whenIsAscii](strings.md#method-fluent-str-when-is-ascii)   |
| [whenIsUlid](strings.md#method-fluent-str-when-is-ulid)           | [whenIsUuid](strings.md#method-fluent-str-when-is-uuid)        | [whenTest](strings.md#method-fluent-str-when-test)          |
| [wordCount](strings.md#method-fluent-str-word-count)              | [words](strings.md#method-fluent-str-words)                    | [wrap](strings.md#method-fluent-str-wrap)                   |

### [Strings](strings.md#strings) <a href="#strings" id="strings"></a>

[**`__()`**](strings.md#method-__)

The `__` function translates the given translation string or translation key using your [language files](../foundation/strings.md/localization/):

```php
echo __('Welcome to our application');
echo __('messages.welcome');
```

If the specified translation string or key does not exist, the `__` function will return the given value. So, using the example above, the `__` function would return `messages.welcome` if that translation key does not exist.

[**`class_basename()`**](strings.md#method-class-basename)

The `class_basename` function returns the class name of the given class with the class's namespace removed:

```php
$class = class_basename('Foo\Bar\Baz');
// Baz
```

[**`e()`**](strings.md#method-e)

The `e` function runs PHP's `htmlspecialchars` function with the `double_encode` option set to `true` by default:

```php
echo e('<html>foo</html>');
// &lt;html&gt;foo&lt;/html&gt;
```

[**`preg_replace_array()`**](strings.md#method-preg-replace-array)

The `preg_replace_array` function replaces a given pattern in the string sequentially using an array:

```php
$string = 'The event will take place between :start and :end';
$replaced = preg_replace_array('/:[a-z_]+/', ['8:30', '9:00'], $string);
// The event will take place between 8:30 and 9:00
```

[**`Str::after()`**](strings.md#method-str-after)

The `Str::after` method returns everything after the given value in a string. The entire string will be returned if the value does not exist within the string:

```php
use Illuminate\Support\Str;
$slice = Str::after('This is my name', 'This is');
// ' my name'
```

[**`Str::afterLast()`**](strings.md#method-str-after-last)

The `Str::afterLast` method returns everything after the last occurrence of the given value in a string. The entire string will be returned if the value does not exist within the string:

```php
use Illuminate\Support\Str;
$slice = Str::afterLast('App\Http\Controllers\Controller', '\\');
// 'Controller'
```

[**`Str::apa()`**](strings.md#method-str-apa)

The `Str::apa` method converts the given string to title case following the [APA guidelines](https://apastyle.apa.org/style-grammar-guidelines/capitalization/title-case):

```php
use Illuminate\Support\Str;
$title = Str::apa('Creating A Project');
// 'Creating a Project'
```

[**`Str::ascii()`**](strings.md#method-str-ascii)

The `Str::ascii` method will attempt to transliterate the string into an ASCII value:

```php
use Illuminate\Support\Str;
$slice = Str::ascii('û');
// 'u'
```

[**`Str::before()`**](strings.md#method-str-before)

The `Str::before` method returns everything before the given value in a string:

```php
use Illuminate\Support\Str;
$slice = Str::before('This is my name', 'my name');
// 'This is '
```

[**`Str::beforeLast()`**](strings.md#method-str-before-last)

The `Str::beforeLast` method returns everything before the last occurrence of the given value in a string:

```php
use Illuminate\Support\Str;
$slice = Str::beforeLast('This is my name', 'is');
// 'This '
```

[**`Str::between()`**](strings.md#method-str-between)

The `Str::between` method returns the portion of a string between two values:

```php
use Illuminate\Support\Str;
$slice = Str::between('This is my name', 'This', 'name');
// ' is my '
```

[**`Str::betweenFirst()`**](strings.md#method-str-between-first)

The `Str::betweenFirst` method returns the smallest possible portion of a string between two values:

```php
use Illuminate\Support\Str;
$slice = Str::betweenFirst('[a] bc [d]', '[', ']');
// 'a'
```

[**`Str::camel()`**](strings.md#method-camel-case)

The `Str::camel` method converts the given string to `camelCase`:

```php
use Illuminate\Support\Str;
$converted = Str::camel('foo_bar');
// 'fooBar'
```

[**`Str::charAt()`**](strings.md#method-char-at)

The `Str::charAt` method returns the character at the specified index. If the index is out of bounds, `false` is returned:

```php
use Illuminate\Support\Str;
$character = Str::charAt('This is my name.', 6);
// 's'
```

[**`Str::chopStart()`**](strings.md#method-str-chop-start)

The `Str::chopStart` method removes the first occurrence of the given value only if the value appears at the start of the string:

```php
use Illuminate\Support\Str;
$url = Str::chopStart('https://laravel.com', 'https://');
// 'laravel.com'
```

You may also pass an array as the second argument. If the string starts with any of the values in the array then that value will be removed from string:

```php
use Illuminate\Support\Str;
$url = Str::chopStart('http://laravel.com', ['https://', 'http://']);
// 'laravel.com'
```

[**`Str::chopEnd()`**](strings.md#method-str-chop-end)

The `Str::chopEnd` method removes the last occurrence of the given value only if the value appears at the end of the string:

```php
use Illuminate\Support\Str;
$url = Str::chopEnd('app/Models/Photograph.php', '.php');
// 'app/Models/Photograph'
```

You may also pass an array as the second argument. If the string ends with any of the values in the array then that value will be removed from string:

```php
use Illuminate\Support\Str;
$url = Str::chopEnd('laravel.com/index.php', ['/index.html', '/index.php']);
// 'laravel.com'
```

[**`Str::contains()`**](strings.md#method-str-contains)

The `Str::contains` method determines if the given string contains the given value. By default this method is case sensitive:

```php
use Illuminate\Support\Str;
$contains = Str::contains('This is my name', 'my');
// true
```

You may also pass an array of values to determine if the given string contains any of the values in the array:

```php
use Illuminate\Support\Str;
$contains = Str::contains('This is my name', ['my', 'foo']);
// true
```

You may disable case sensitivity by setting the `ignoreCase` argument to `true`:

```php
use Illuminate\Support\Str;
$contains = Str::contains('This is my name', 'MY', ignoreCase: true);
// true
```

[**`Str::containsAll()`**](strings.md#method-str-contains-all)

The `Str::containsAll` method determines if the given string contains all of the values in a given array:

```php
use Illuminate\Support\Str;
$containsAll = Str::containsAll('This is my name', ['my', 'name']);
// true
```

You may disable case sensitivity by setting the `ignoreCase` argument to `true`:

```php
use Illuminate\Support\Str;
$containsAll = Str::containsAll('This is my name', ['MY', 'NAME'], ignoreCase: true);
// true
```

[**`Str::doesntContain()`**](strings.md#method-str-doesnt-contain)

The `Str::doesntContain` method determines if the given string doesn't contain the given value. By default this method is case sensitive:

```php
use Illuminate\Support\Str;
$doesntContain = Str::doesntContain('This is name', 'my');
// true
```

You may also pass an array of values to determine if the given string doesn't contain any of the values in the array:

```php
use Illuminate\Support\Str;
$doesntContain = Str::doesntContain('This is name', ['my', 'foo']);
// true
```

You may disable case sensitivity by setting the `ignoreCase` argument to `true`:

```php
use Illuminate\Support\Str;
$doesntContain = Str::doesntContain('This is name', 'MY', ignoreCase: true);
// true
```

[**`Str::deduplicate()`**](strings.md#method-deduplicate)

The `Str::deduplicate` method replaces consecutive instances of a character with a single instance of that character in the given string. By default, the method deduplicates spaces:

```php
use Illuminate\Support\Str;
$result = Str::deduplicate('The   Laravel   Framework');
// The Laravel Framework
```

You may specify a different character to deduplicate by passing it in as the second argument to the method:

```php
use Illuminate\Support\Str;
$result = Str::deduplicate('The---Laravel---Framework', '-');
// The-Laravel-Framework
```

[**`Str::endsWith()`**](strings.md#method-ends-with)

The `Str::endsWith` method determines if the given string ends with the given value:

```php
use Illuminate\Support\Str;
$result = Str::endsWith('This is my name', 'name');
// true
```

You may also pass an array of values to determine if the given string ends with any of the values in the array:

```php
use Illuminate\Support\Str;
$result = Str::endsWith('This is my name', ['name', 'foo']);
// true
$result = Str::endsWith('This is my name', ['this', 'foo']);
// false
```

[**`Str::excerpt()`**](strings.md#method-excerpt)

The `Str::excerpt` method extracts an excerpt from a given string that matches the first instance of a phrase within that string:

```php
use Illuminate\Support\Str;
$excerpt = Str::excerpt('This is my name', 'my', [    'radius' => 3]);
// '...is my na...'
```

The `radius` option, which defaults to `100`, allows you to define the number of characters that should appear on each side of the truncated string.

In addition, you may use the `omission` option to define the string that will be prepended and appended to the truncated string:

```php
use Illuminate\Support\Str;
$excerpt = Str::excerpt('This is my name', 'name', [    'radius' => 3,    'omission' => '(...) ']);
// '(...) my name'
```

[**`Str::finish()`**](strings.md#method-str-finish)

The `Str::finish` method adds a single instance of the given value to a string if it does not already end with that value:

```php
use Illuminate\Support\Str;
$adjusted = Str::finish('this/string', '/');
// this/string/
$adjusted = Str::finish('this/string/', '/');
// this/string/
```

[**`Str::headline()`**](strings.md#method-str-headline)

The `Str::headline` method will convert strings delimited by casing, hyphens, or underscores into a space delimited string with each word's first letter capitalized:

```php
use Illuminate\Support\Str;
$headline = Str::headline('steve_jobs');
// Steve Jobs
$headline = Str::headline('EmailNotificationSent');
// Email Notification Sent
```

[**`Str::inlineMarkdown()`**](strings.md#method-str-inline-markdown)

The `Str::inlineMarkdown` method converts GitHub flavored Markdown into inline HTML using [CommonMark](https://commonmark.thephpleague.com/). However, unlike the `markdown` method, it does not wrap all generated HTML in a block-level element:

```php
use Illuminate\Support\Str;
$html = Str::inlineMarkdown('**Laravel**');
// <strong>Laravel</strong>
```

**Markdown Security**

By default, Markdown supports raw HTML, which will expose Cross-Site Scripting (XSS) vulnerabilities when used with raw user input. As per the [CommonMark Security documentation](https://commonmark.thephpleague.com/security/), you may use the `html_input` option to either escape or strip raw HTML, and the `allow_unsafe_links` option to specify whether to allow unsafe links. If you need to allow some raw HTML, you should pass your compiled Markdown through an HTML Purifier:

```php
use Illuminate\Support\Str;
Str::inlineMarkdown('Inject: <script>alert("Hello XSS!");</script>', [    'html_input' => 'strip',    'allow_unsafe_links' => false,]);
// Inject: alert(&quot;Hello XSS!&quot;);
```

[**`Str::is()`**](strings.md#method-str-is)

The `Str::is` method determines if a given string matches a given pattern. Asterisks may be used as wildcard values:

```php
use Illuminate\Support\Str;
$matches = Str::is('foo*', 'foobar');
// true
$matches = Str::is('baz*', 'foobar');
// false
```

You may disable case sensitivity by setting the `ignoreCase` argument to `true`:

```php
use Illuminate\Support\Str;
$matches = Str::is('*.jpg', 'photo.JPG', ignoreCase: true);
// true
```

[**`Str::isAscii()`**](strings.md#method-str-is-ascii)

The `Str::isAscii` method determines if a given string is 7 bit ASCII:

```php
use Illuminate\Support\Str;
$isAscii = Str::isAscii('Taylor');
// true
$isAscii = Str::isAscii('ü');
// false
```

[**`Str::isJson()`**](strings.md#method-str-is-json)

The `Str::isJson` method determines if the given string is valid JSON:

```php
use Illuminate\Support\Str;
$result = Str::isJson('[1,2,3]');
// true
$result = Str::isJson('{"first": "John", "last": "Doe"}');
// true
$result = Str::isJson('{first: "John", last: "Doe"}');
// false
```

[**`Str::isUrl()`**](strings.md#method-str-is-url)

The `Str::isUrl` method determines if the given string is a valid URL:

```php
use Illuminate\Support\Str;
$isUrl = Str::isUrl('http://example.com');
// true
$isUrl = Str::isUrl('laravel');
// false
```

The `isUrl` method considers a wide range of protocols as valid. However, you may specify the protocols that should be considered valid by providing them to the `isUrl` method:

```php
$isUrl = Str::isUrl('http://example.com', ['http', 'https']);
```

[**`Str::isUlid()`**](strings.md#method-str-is-ulid)

The `Str::isUlid` method determines if the given string is a valid ULID:

```php
use Illuminate\Support\Str;
$isUlid = Str::isUlid('01gd6r360bp37zj17nxb55yv40');
// true
$isUlid = Str::isUlid('laravel');
// false
```

[**`Str::isUuid()`**](strings.md#method-str-is-uuid)

The `Str::isUuid` method determines if the given string is a valid UUID:

```php
use Illuminate\Support\Str;
$isUuid = Str::isUuid('a0a2a2d2-0b87-4a18-83f2-2529882be2de');
// true
$isUuid = Str::isUuid('laravel');
// false
```

[**`Str::kebab()`**](strings.md#method-kebab-case)

The `Str::kebab` method converts the given string to `kebab-case`:

```php
use Illuminate\Support\Str;
$converted = Str::kebab('fooBar');
// foo-bar
```

[**`Str::lcfirst()`**](strings.md#method-str-lcfirst)

The `Str::lcfirst` method returns the given string with the first character lowercased:

```php
use Illuminate\Support\Str;
$string = Str::lcfirst('Foo Bar');
// foo Bar
```

[**`Str::length()`**](strings.md#method-str-length)

The `Str::length` method returns the length of the given string:

```php
use Illuminate\Support\Str;
$length = Str::length('Laravel');
// 7
```

[**`Str::limit()`**](strings.md#method-str-limit)

The `Str::limit` method truncates the given string to the specified length:

```php
use Illuminate\Support\Str;
$truncated = Str::limit('The quick brown fox jumps over the lazy dog', 20);
// The quick brown fox...
```

You may pass a third argument to the method to change the string that will be appended to the end of the truncated string:

```php
$truncated = Str::limit('The quick brown fox jumps over the lazy dog', 20, ' (...)');
// The quick brown fox (...)
```

If you would like to preserve complete words when truncating the string, you may utilize the `preserveWords` argument. When this argument is `true`, the string will be truncated to the nearest complete word boundary:

```php
$truncated = Str::limit('The quick brown fox', 12, preserveWords: true);
// The quick...
```

[**`Str::lower()`**](strings.md#method-str-lower)

The `Str::lower` method converts the given string to lowercase:

```php
use Illuminate\Support\Str;
$converted = Str::lower('LARAVEL');
// laravel
```

[**`Str::markdown()`**](strings.md#method-str-markdown)

The `Str::markdown` method converts GitHub flavored Markdown into HTML using [CommonMark](https://commonmark.thephpleague.com/):

```php
use Illuminate\Support\Str;
$html = Str::markdown('# Laravel');
// <h1>Laravel</h1>
$html = Str::markdown('# Taylor <b>Otwell</b>', [    'html_input' => 'strip',]);
// <h1>Taylor Otwell</h1>
```

**Markdown Security**

By default, Markdown supports raw HTML, which will expose Cross-Site Scripting (XSS) vulnerabilities when used with raw user input. As per the [CommonMark Security documentation](https://commonmark.thephpleague.com/security/), you may use the `html_input` option to either escape or strip raw HTML, and the `allow_unsafe_links` option to specify whether to allow unsafe links. If you need to allow some raw HTML, you should pass your compiled Markdown through an HTML Purifier:

```php
use Illuminate\Support\Str;
Str::markdown('Inject: <script>alert("Hello XSS!");</script>', [    'html_input' => 'strip',    'allow_unsafe_links' => false,]);
// <p>Inject: alert(&quot;Hello XSS!&quot;);</p>
```

[**`Str::mask()`**](strings.md#method-str-mask)

The `Str::mask` method masks a portion of a string with a repeated character, and may be used to obfuscate segments of strings such as email addresses and phone numbers:

```php
use Illuminate\Support\Str;
$string = Str::mask('taylor@example.com', '*', 3);
// tay***************
```

If needed, you provide a negative number as the third argument to the `mask` method, which will instruct the method to begin masking at the given distance from the end of the string:

```php
$string = Str::mask('taylor@example.com', '*', -15, 3);
// tay***@example.com
```

[**`Str::orderedUuid()`**](strings.md#method-str-ordered-uuid)

The `Str::orderedUuid` method generates a "timestamp first" UUID that may be efficiently stored in an indexed database column. Each UUID that is generated using this method will be sorted after UUIDs previously generated using the method:

```php
use Illuminate\Support\Str;
return (string) Str::orderedUuid();
```

[**`Str::padBoth()`**](strings.md#method-str-padboth)

The `Str::padBoth` method wraps PHP's `str_pad` function, padding both sides of a string with another string until the final string reaches a desired length:

```php
use Illuminate\Support\Str;
$padded = Str::padBoth('James', 10, '_');
// '__James___'
$padded = Str::padBoth('James', 10);
// '  James   '
```

[**`Str::padLeft()`**](strings.md#method-str-padleft)

The `Str::padLeft` method wraps PHP's `str_pad` function, padding the left side of a string with another string until the final string reaches a desired length:

```php
use Illuminate\Support\Str;
$padded = Str::padLeft('James', 10, '-=');
// '-=-=-James'
$padded = Str::padLeft('James', 10);
// '     James'
```

[**`Str::padRight()`**](strings.md#method-str-padright)

The `Str::padRight` method wraps PHP's `str_pad` function, padding the right side of a string with another string until the final string reaches a desired length:

```php
use Illuminate\Support\Str;
$padded = Str::padRight('James', 10, '-');
// 'James-----'
$padded = Str::padRight('James', 10);
// 'James     '
```

[**`Str::password()`**](strings.md#method-str-password)

The `Str::password` method may be used to generate a secure, random password of a given length. The password will consist of a combination of letters, numbers, symbols, and spaces. By default, passwords are 32 characters long:

```php
use Illuminate\Support\Str;
$password = Str::password();
// 'EbJo2vE-AS:U,$%_gkrV4n,q~1xy/-_4'
$password = Str::password(12);
// 'qwuar>#V|i]N'
```

[**`Str::plural()`**](strings.md#method-str-plural)

The `Str::plural` method converts a singular word string to its plural form. This function supports [any of the languages support by Laravel's pluralizer](../foundation/strings.md/localization/#pluralization-language):

```php
use Illuminate\Support\Str;
$plural = Str::plural('car');
// cars
$plural = Str::plural('child');
// children
```

You may provide an integer as a second argument to the function to retrieve the singular or plural form of the string:

```php
use Illuminate\Support\Str;
$plural = Str::plural('child', 2);
// children
$singular = Str::plural('child', 1);
// child
```

[**`Str::pluralStudly()`**](strings.md#method-str-plural-studly)

The `Str::pluralStudly` method converts a singular word string formatted in studly caps case to its plural form. This function supports [any of the languages support by Laravel's pluralizer](../foundation/strings.md/localization/#pluralization-language):

```php
use Illuminate\Support\Str;
$plural = Str::pluralStudly('VerifiedHuman');
// VerifiedHumans
$plural = Str::pluralStudly('UserFeedback');
// UserFeedback
```

You may provide an integer as a second argument to the function to retrieve the singular or plural form of the string:

```php
use Illuminate\Support\Str;
$plural = Str::pluralStudly('VerifiedHuman', 2);
// VerifiedHumans
$singular = Str::pluralStudly('VerifiedHuman', 1);
// VerifiedHuman
```

[**`Str::position()`**](strings.md#method-str-position)

The `Str::position` method returns the position of the first occurrence of a substring in a string. If the substring does not exist in the given string, `false` is returned:

```php
use Illuminate\Support\Str;
$position = Str::position('Hello, World!', 'Hello');
// 0
$position = Str::position('Hello, World!', 'W');
// 7
```

[**`Str::random()`**](strings.md#method-str-random)

The `Str::random` method generates a random string of the specified length. This function uses PHP's `random_bytes` function:

```php
use Illuminate\Support\Str;
$random = Str::random(40);
```

During testing, it may be useful to "fake" the value that is returned by the `Str::random` method. To accomplish this, you may use the `createRandomStringsUsing` method:

```php
Str::createRandomStringsUsing(function () {    return 'fake-random-string';});
```

To instruct the `random` method to return to generating random strings normally, you may invoke the `createRandomStringsNormally` method:

```php
Str::createRandomStringsNormally();
```

[**`Str::remove()`**](strings.md#method-str-remove)

The `Str::remove` method removes the given value or array of values from the string:

```php
use Illuminate\Support\Str;
$string = 'Peter Piper picked a peck of pickled peppers.';
$removed = Str::remove('e', $string);
// Ptr Pipr pickd a pck of pickld ppprs.
```

You may also pass `false` as a third argument to the `remove` method to ignore case when removing strings.

[**`Str::repeat()`**](strings.md#method-str-repeat)

The `Str::repeat` method repeats the given string:

```php
use Illuminate\Support\Str;
$string = 'a';
$repeat = Str::repeat($string, 5);
// aaaaa
```

[**`Str::replace()`**](strings.md#method-str-replace)

The `Str::replace` method replaces a given string within the string:

```php
use Illuminate\Support\Str;
$string = 'Laravel 10.x';
$replaced = Str::replace('10.x', '11.x', $string);
// Laravel 11.x
```

The `replace` method also accepts a `caseSensitive` argument. By default, the `replace` method is case sensitive:

```php
Str::replace('Framework', 'Laravel', caseSensitive: false);
```

[**`Str::replaceArray()`**](strings.md#method-str-replace-array)

The `Str::replaceArray` method replaces a given value in the string sequentially using an array:

```php
use Illuminate\Support\Str;
$string = 'The event will take place between ? and ?';
$replaced = Str::replaceArray('?', ['8:30', '9:00'], $string);
// The event will take place between 8:30 and 9:00
```

[**`Str::replaceFirst()`**](strings.md#method-str-replace-first)

The `Str::replaceFirst` method replaces the first occurrence of a given value in a string:

```php
use Illuminate\Support\Str;
$replaced = Str::replaceFirst('the', 'a', 'the quick brown fox jumps over the lazy dog');
// a quick brown fox jumps over the lazy dog
```

[**`Str::replaceLast()`**](strings.md#method-str-replace-last)

The `Str::replaceLast` method replaces the last occurrence of a given value in a string:

```php
use Illuminate\Support\Str;
$replaced = Str::replaceLast('the', 'a', 'the quick brown fox jumps over the lazy dog');
// the quick brown fox jumps over a lazy dog
```

[**`Str::replaceMatches()`**](strings.md#method-str-replace-matches)

The `Str::replaceMatches` method replaces all portions of a string matching a pattern with the given replacement string:

```php
use Illuminate\Support\Str;
$replaced = Str::replaceMatches(    pattern: '/[^A-Za-z0-9]++/',    replace: '',    subject: '(+1) 501-555-1000')
// '15015551000'
```

The `replaceMatches` method also accepts a closure that will be invoked with each portion of the string matching the given pattern, allowing you to perform the replacement logic within the closure and return the replaced value:

```php
use Illuminate\Support\Str;
$replaced = Str::replaceMatches('/\d/', function (array $matches) {    return '['.$matches[0].']';}, '123');
// '[1][2][3]'
```

[**`Str::replaceStart()`**](strings.md#method-str-replace-start)

The `Str::replaceStart` method replaces the first occurrence of the given value only if the value appears at the start of the string:

```php
use Illuminate\Support\Str;
$replaced = Str::replaceStart('Hello', 'Laravel', 'Hello World');
// Laravel World
$replaced = Str::replaceStart('World', 'Laravel', 'Hello World');
// Hello World
```

[**`Str::replaceEnd()`**](strings.md#method-str-replace-end)

The `Str::replaceEnd` method replaces the last occurrence of the given value only if the value appears at the end of the string:

```php
use Illuminate\Support\Str;
$replaced = Str::replaceEnd('World', 'Laravel', 'Hello World');
// Hello Laravel
$replaced = Str::replaceEnd('Hello', 'Laravel', 'Hello World');
// Hello World
```

[**`Str::reverse()`**](strings.md#method-str-reverse)

The `Str::reverse` method reverses the given string:

```php
use Illuminate\Support\Str;
$reversed = Str::reverse('Hello World');
// dlroW olleH
```

[**`Str::singular()`**](strings.md#method-str-singular)

The `Str::singular` method converts a string to its singular form. This function supports [any of the languages support by Laravel's pluralizer](../foundation/strings.md/localization/#pluralization-language):

```php
use Illuminate\Support\Str;
$singular = Str::singular('cars');
// car
$singular = Str::singular('children');
// child
```

[**`Str::slug()`**](strings.md#method-str-slug)

The `Str::slug` method generates a URL friendly "slug" from the given string:

```php
use Illuminate\Support\Str;
$slug = Str::slug('Laravel 5 Framework', '-');
// laravel-5-framework
```

[**`Str::snake()`**](strings.md#method-snake-case)

The `Str::snake` method converts the given string to `snake_case`:

```php
use Illuminate\Support\Str;
$converted = Str::snake('fooBar');
// foo_bar
$converted = Str::snake('fooBar', '-');
// foo-bar
```

[**`Str::squish()`**](strings.md#method-str-squish)

The `Str::squish` method removes all extraneous white space from a string, including extraneous white space between words:

```php
use Illuminate\Support\Str;
$string = Str::squish('    laravel    framework    ');
// laravel framework
```

[**`Str::start()`**](strings.md#method-str-start)

The `Str::start` method adds a single instance of the given value to a string if it does not already start with that value:

```php
use Illuminate\Support\Str;
$adjusted = Str::start('this/string', '/');
// /this/string
$adjusted = Str::start('/this/string', '/');
// /this/string
```

[**`Str::startsWith()`**](strings.md#method-starts-with)

The `Str::startsWith` method determines if the given string begins with the given value:

```php
use Illuminate\Support\Str;
$result = Str::startsWith('This is my name', 'This');
// true
```

If an array of possible values is passed, the `startsWith` method will return `true` if the string begins with any of the given values:

```php
$result = Str::startsWith('This is my name', ['This', 'That', 'There']);
// true
```

[**`Str::studly()`**](strings.md#method-studly-case)

The `Str::studly` method converts the given string to `StudlyCase`:

```php
use Illuminate\Support\Str;
$converted = Str::studly('foo_bar');
// FooBar
```

[**`Str::substr()`**](strings.md#method-str-substr)

The `Str::substr` method returns the portion of string specified by the start and length parameters:

```php
use Illuminate\Support\Str;
$converted = Str::substr('The Laravel Framework', 4, 7);
// Laravel
```

[**`Str::substrCount()`**](strings.md#method-str-substrcount)

The `Str::substrCount` method returns the number of occurrences of a given value in the given string:

```php
use Illuminate\Support\Str;
$count = Str::substrCount('If you like ice cream, you will like snow cones.', 'like');
// 2
```

[**`Str::substrReplace()`**](strings.md#method-str-substrreplace)

The `Str::substrReplace` method replaces text within a portion of a string, starting at the position specified by the third argument and replacing the number of characters specified by the fourth argument. Passing `0` to the method's fourth argument will insert the string at the specified position without replacing any of the existing characters in the string:

```php
use Illuminate\Support\Str;
$result = Str::substrReplace('1300', ':', 2);// 13:
$result = Str::substrReplace('1300', ':', 2, 0);// 13:00
```

[**`Str::swap()`**](strings.md#method-str-swap)

The `Str::swap` method replaces multiple values in the given string using PHP's `strtr` function:

```php
use Illuminate\Support\Str;
$string = Str::swap([    'Tacos' => 'Burritos',    'great' => 'fantastic',], 'Tacos are great!');
// Burritos are fantastic!
```

[**`Str::take()`**](strings.md#method-take)

The `Str::take` method returns a specified number of characters from the beginning of a string:

```php
use Illuminate\Support\Str;
$taken = Str::take('Build something amazing!', 5);
// Build
```

[**`Str::title()`**](strings.md#method-title-case)

The `Str::title` method converts the given string to `Title Case`:

```php
use Illuminate\Support\Str;
$converted = Str::title('a nice title uses the correct case');
// A Nice Title Uses The Correct Case
```

[**`Str::toBase64()`**](strings.md#method-str-to-base64)

The `Str::toBase64` method converts the given string to Base64:

```php
use Illuminate\Support\Str;
$base64 = Str::toBase64('Laravel');
// TGFyYXZlbA==
```

[**`Str::transliterate()`**](strings.md#method-str-transliterate)

The `Str::transliterate` method will attempt to convert a given string into its closest ASCII representation:

```php
use Illuminate\Support\Str;
$email = Str::transliterate('ⓣⓔⓢⓣ@ⓛⓐⓡⓐⓥⓔⓛ.ⓒⓞⓜ');
// 'test@laravel.com'
```

[**`Str::trim()`**](strings.md#method-str-trim)

The `Str::trim` method strips whitespace (or other characters) from the beginning and end of the given string. Unlike PHP's native `trim` function, the `Str::trim` method also removes unicode whitespace characters:

```php
use Illuminate\Support\Str;
$string = Str::trim(' foo bar ');
// 'foo bar'
```

[**`Str::ltrim()`**](strings.md#method-str-ltrim)

The `Str::ltrim` method strips whitespace (or other characters) from the beginning of the given string. Unlike PHP's native `ltrim` function, the `Str::ltrim` method also removes unicode whitespace characters:

```php
use Illuminate\Support\Str;
$string = Str::ltrim('  foo bar  ');
// 'foo bar  '
```

[**`Str::rtrim()`**](strings.md#method-str-rtrim)

The `Str::rtrim` method strips whitespace (or other characters) from the end of the given string. Unlike PHP's native `rtrim` function, the `Str::rtrim` method also removes unicode whitespace characters:

```php
use Illuminate\Support\Str;
$string = Str::rtrim('  foo bar  ');
// '  foo bar'
```

[**`Str::ucfirst()`**](strings.md#method-str-ucfirst)

The `Str::ucfirst` method returns the given string with the first character capitalized:

```php
use Illuminate\Support\Str;
$string = Str::ucfirst('foo bar');
// Foo bar
```

[**`Str::ucsplit()`**](strings.md#method-str-ucsplit)

The `Str::ucsplit` method splits the given string into an array by uppercase characters:

```php
use Illuminate\Support\Str;
$segments = Str::ucsplit('FooBar');
// [0 => 'Foo', 1 => 'Bar']
```

[**`Str::upper()`**](strings.md#method-str-upper)

The `Str::upper` method converts the given string to uppercase:

```php
use Illuminate\Support\Str;
$string = Str::upper('laravel');
// LARAVEL
```

[**`Str::ulid()`**](strings.md#method-str-ulid)

The `Str::ulid` method generates a ULID, which is a compact, time-ordered unique identifier:

```php
use Illuminate\Support\Str;
return (string) Str::ulid();
// 01gd6r360bp37zj17nxb55yv40
```

If you would like to retrieve a `Illuminate\Support\Carbon` date instance representing the date and time that a given ULID was created, you may use the `createFromId` method provided by Laravel's Carbon integration:

```php
use Illuminate\Support\Carbon;use Illuminate\Support\Str;
$date = Carbon::createFromId((string) Str::ulid());
```

During testing, it may be useful to "fake" the value that is returned by the `Str::ulid` method. To accomplish this, you may use the `createUlidsUsing` method:

```php
use Symfony\Component\Uid\Ulid;
Str::createUlidsUsing(function () {    return new Ulid('01HRDBNHHCKNW2AK4Z29SN82T9');});
```

To instruct the `ulid` method to return to generating ULIDs normally, you may invoke the `createUlidsNormally` method:

```php
Str::createUlidsNormally();
```

[**`Str::unwrap()`**](strings.md#method-str-unwrap)

The `Str::unwrap` method removes the specified strings from the beginning and end of a given string:

```php
use Illuminate\Support\Str;
Str::unwrap('-Laravel-', '-');
// Laravel
Str::unwrap('{framework: "Laravel"}', '{', '}');
// framework: "Laravel"
```

[**`Str::uuid()`**](strings.md#method-str-uuid)

The `Str::uuid` method generates a UUID (version 4):

```php
use Illuminate\Support\Str;
return (string) Str::uuid();
```

During testing, it may be useful to "fake" the value that is returned by the `Str::uuid` method. To accomplish this, you may use the `createUuidsUsing` method:

```php
use Ramsey\Uuid\Uuid;
Str::createUuidsUsing(function () {    return Uuid::fromString('eadbfeac-5258-45c2-bab7-ccb9b5ef74f9');});
```

To instruct the `uuid` method to return to generating UUIDs normally, you may invoke the `createUuidsNormally` method:

```php
Str::createUuidsNormally();
```

[**`Str::wordCount()`**](strings.md#method-str-word-count)

The `Str::wordCount` method returns the number of words that a string contains:

```php
use Illuminate\Support\Str;
Str::wordCount('Hello, world!'); // 2
```

[**`Str::wordWrap()`**](strings.md#method-str-word-wrap)

The `Str::wordWrap` method wraps a string to a given number of characters:

```php
use Illuminate\Support\Str;
$text = "The quick brown fox jumped over the lazy dog."
Str::wordWrap($text, characters: 20, break: "<br />\n");
/*The quick brown fox<br />jumped over the lazy<br />dog.*/
```

[**`Str::words()`**](strings.md#method-str-words)

The `Str::words` method limits the number of words in a string. An additional string may be passed to this method via its third argument to specify which string should be appended to the end of the truncated string:

```php
use Illuminate\Support\Str;
return Str::words('Perfectly balanced, as all things should be.', 3, ' >>>');
// Perfectly balanced, as >>>
```

[**`Str::wrap()`**](strings.md#method-str-wrap)

The `Str::wrap` method wraps the given string with an additional string or pair of strings:

```php
use Illuminate\Support\Str;
Str::wrap('Laravel', '"');
// "Laravel"
Str::wrap('is', before: 'This ', after: ' Laravel!');
// This is Laravel!
```

[**`str()`**](strings.md#method-str)

The `str` function returns a new `Illuminate\Support\Stringable` instance of the given string. This function is equivalent to the `Str::of` method:

```php
$string = str('Taylor')->append(' Otwell');
// 'Taylor Otwell'
```

If no argument is provided to the `str` function, the function returns an instance of `Illuminate\Support\Str`:

```php
$snake = str()->snake('FooBar');
// 'foo_bar'
```

[**`trans()`**](strings.md#method-trans)

The `trans` function translates the given translation key using your [language files](../foundation/strings.md/localization/):

```php
echo trans('messages.welcome');
```

If the specified translation key does not exist, the `trans` function will return the given key. So, using the example above, the `trans` function would return `messages.welcome` if the translation key does not exist.

[**`trans_choice()`**](strings.md#method-trans-choice)

The `trans_choice` function translates the given translation key with inflection:

```php
echo trans_choice('messages.notifications', $unreadCount);
```

If the specified translation key does not exist, the `trans_choice` function will return the given key. So, using the example above, the `trans_choice` function would return `messages.notifications` if the translation key does not exist.

### [Fluent Strings](strings.md#fluent-strings) <a href="#fluent-strings" id="fluent-strings"></a>

Fluent strings provide a more fluent, object-oriented interface for working with string values, allowing you to chain multiple string operations together using a more readable syntax compared to traditional string operations.

[**`after`**](strings.md#method-fluent-str-after)

The `after` method returns everything after the given value in a string. The entire string will be returned if the value does not exist within the string:

```php
use Illuminate\Support\Str;
$slice = Str::of('This is my name')->after('This is');
// ' my name'
```

[**`afterLast`**](strings.md#method-fluent-str-after-last)

The `afterLast` method returns everything after the last occurrence of the given value in a string. The entire string will be returned if the value does not exist within the string:

```php
use Illuminate\Support\Str;
$slice = Str::of('App\Http\Controllers\Controller')->afterLast('\\');
// 'Controller'
```

[**`apa`**](strings.md#method-fluent-str-apa)

The `apa` method converts the given string to title case following the [APA guidelines](https://apastyle.apa.org/style-grammar-guidelines/capitalization/title-case):

```php
use Illuminate\Support\Str;
$converted = Str::of('a nice title uses the correct case')->apa();
// A Nice Title Uses the Correct Case
```

[**`append`**](strings.md#method-fluent-str-append)

The `append` method appends the given values to the string:

```php
use Illuminate\Support\Str;
$string = Str::of('Taylor')->append(' Otwell');
// 'Taylor Otwell'
```

[**`ascii`**](strings.md#method-fluent-str-ascii)

The `ascii` method will attempt to transliterate the string into an ASCII value:

```php
use Illuminate\Support\Str;
$string = Str::of('ü')->ascii();
// 'u'
```

[**`basename`**](strings.md#method-fluent-str-basename)

The `basename` method will return the trailing name component of the given string:

```php
use Illuminate\Support\Str;
$string = Str::of('/foo/bar/baz')->basename();
// 'baz'
```

If needed, you may provide an "extension" that will be removed from the trailing component:

```php
use Illuminate\Support\Str;
$string = Str::of('/foo/bar/baz.jpg')->basename('.jpg');
// 'baz'
```

[**`before`**](strings.md#method-fluent-str-before)

The `before` method returns everything before the given value in a string:

```php
use Illuminate\Support\Str;
$slice = Str::of('This is my name')->before('my name');
// 'This is '
```

[**`beforeLast`**](strings.md#method-fluent-str-before-last)

The `beforeLast` method returns everything before the last occurrence of the given value in a string:

```php
use Illuminate\Support\Str;
$slice = Str::of('This is my name')->beforeLast('is');
// 'This '
```

[**`between`**](strings.md#method-fluent-str-between)

The `between` method returns the portion of a string between two values:

```php
use Illuminate\Support\Str;
$converted = Str::of('This is my name')->between('This', 'name');
// ' is my '
```

[**`betweenFirst`**](strings.md#method-fluent-str-between-first)

The `betweenFirst` method returns the smallest possible portion of a string between two values:

```php
use Illuminate\Support\Str;
$converted = Str::of('[a] bc [d]')->betweenFirst('[', ']');
// 'a'
```

[**`camel`**](strings.md#method-fluent-str-camel)

The `camel` method converts the given string to `camelCase`:

```php
use Illuminate\Support\Str;
$converted = Str::of('foo_bar')->camel();
// 'fooBar'
```

[**`charAt`**](strings.md#method-fluent-str-char-at)

The `charAt` method returns the character at the specified index. If the index is out of bounds, `false` is returned:

```php
use Illuminate\Support\Str;
$character = Str::of('This is my name.')->charAt(6);
// 's'
```

[**`classBasename`**](strings.md#method-fluent-str-class-basename)

The `classBasename` method returns the class name of the given class with the class's namespace removed:

```php
use Illuminate\Support\Str;
$class = Str::of('Foo\Bar\Baz')->classBasename();
// 'Baz'
```

[**`chopStart`**](strings.md#method-fluent-str-chop-start)

The `chopStart` method removes the first occurrence of the given value only if the value appears at the start of the string:

```php
use Illuminate\Support\Str;
$url = Str::of('https://laravel.com')->chopStart('https://');
// 'laravel.com'
```

You may also pass an array. If the string starts with any of the values in the array then that value will be removed from string:

```php
use Illuminate\Support\Str;
$url = Str::of('http://laravel.com')->chopStart(['https://', 'http://']);
// 'laravel.com'
```

[**`chopEnd`**](strings.md#method-fluent-str-chop-end)

The `chopEnd` method removes the last occurrence of the given value only if the value appears at the end of the string:

```php
use Illuminate\Support\Str;
$url = Str::of('https://laravel.com')->chopEnd('.com');
// 'https://laravel'
```

You may also pass an array. If the string ends with any of the values in the array then that value will be removed from string:

```php
use Illuminate\Support\Str;
$url = Str::of('http://laravel.com')->chopEnd(['.com', '.io']);
// 'http://laravel'
```

[**`contains`**](strings.md#method-fluent-str-contains)

The `contains` method determines if the given string contains the given value. By default this method is case sensitive:

```php
use Illuminate\Support\Str;
$contains = Str::of('This is my name')->contains('my');
// true
```

You may also pass an array of values to determine if the given string contains any of the values in the array:

```php
use Illuminate\Support\Str;
$contains = Str::of('This is my name')->contains(['my', 'foo']);
// true
```

You can disable case sensitivity by setting the `ignoreCase` argument to `true`:

```php
use Illuminate\Support\Str;
$contains = Str::of('This is my name')->contains('MY', ignoreCase: true);
// true
```

[**`containsAll`**](strings.md#method-fluent-str-contains-all)

The `containsAll` method determines if the given string contains all of the values in the given array:

```php
use Illuminate\Support\Str;
$containsAll = Str::of('This is my name')->containsAll(['my', 'name']);
// true
```

You can disable case sensitivity by setting the `ignoreCase` argument to `true`:

```php
use Illuminate\Support\Str;
$containsAll = Str::of('This is my name')->containsAll(['MY', 'NAME'], ignoreCase: true);
// true
```

[**`deduplicate`**](strings.md#method-fluent-str-deduplicate)

The `deduplicate` method replaces consecutive instances of a character with a single instance of that character in the given string. By default, the method deduplicates spaces:

```php
use Illuminate\Support\Str;
$result = Str::of('The   Laravel   Framework')->deduplicate();
// The Laravel Framework
```

You may specify a different character to deduplicate by passing it in as the second argument to the method:

```php
use Illuminate\Support\Str;
$result = Str::of('The---Laravel---Framework')->deduplicate('-');
// The-Laravel-Framework
```

[**`dirname`**](strings.md#method-fluent-str-dirname)

The `dirname` method returns the parent directory portion of the given string:

```php
use Illuminate\Support\Str;
$string = Str::of('/foo/bar/baz')->dirname();
// '/foo/bar'
```

If necessary, you may specify how many directory levels you wish to trim from the string:

```php
use Illuminate\Support\Str;
$string = Str::of('/foo/bar/baz')->dirname(2);
// '/foo'
```

[**`endsWith`**](strings.md#method-fluent-str-ends-with)

The `endsWith` method determines if the given string ends with the given value:

```php
use Illuminate\Support\Str;
$result = Str::of('This is my name')->endsWith('name');
// true
```

You may also pass an array of values to determine if the given string ends with any of the values in the array:

```php
use Illuminate\Support\Str;
$result = Str::of('This is my name')->endsWith(['name', 'foo']);
// true
$result = Str::of('This is my name')->endsWith(['this', 'foo']);
// false
```

[**`exactly`**](strings.md#method-fluent-str-exactly)

The `exactly` method determines if the given string is an exact match with another string:

```php
use Illuminate\Support\Str;
$result = Str::of('Laravel')->exactly('Laravel');
// true
```

[**`excerpt`**](strings.md#method-fluent-str-excerpt)

The `excerpt` method extracts an excerpt from the string that matches the first instance of a phrase within that string:

```php
use Illuminate\Support\Str;
$excerpt = Str::of('This is my name')->excerpt('my', [    'radius' => 3]);
// '...is my na...'
```

The `radius` option, which defaults to `100`, allows you to define the number of characters that should appear on each side of the truncated string.

In addition, you may use the `omission` option to change the string that will be prepended and appended to the truncated string:

```php
use Illuminate\Support\Str;
$excerpt = Str::of('This is my name')->excerpt('name', [    'radius' => 3,    'omission' => '(...) ']);
// '(...) my name'
```

[**`explode`**](strings.md#method-fluent-str-explode)

The `explode` method splits the string by the given delimiter and returns a collection containing each section of the split string:

```php
use Illuminate\Support\Str;
$collection = Str::of('foo bar baz')->explode(' ');
// collect(['foo', 'bar', 'baz'])
```

[**`finish`**](strings.md#method-fluent-str-finish)

The `finish` method adds a single instance of the given value to a string if it does not already end with that value:

```php
use Illuminate\Support\Str;
$adjusted = Str::of('this/string')->finish('/');
// this/string/
$adjusted = Str::of('this/string/')->finish('/');
// this/string/
```

[**`headline`**](strings.md#method-fluent-str-headline)

The `headline` method will convert strings delimited by casing, hyphens, or underscores into a space delimited string with each word's first letter capitalized:

```php
use Illuminate\Support\Str;
$headline = Str::of('taylor_otwell')->headline();
// Taylor Otwell
$headline = Str::of('EmailNotificationSent')->headline();
// Email Notification Sent
```

[**`inlineMarkdown`**](strings.md#method-fluent-str-inline-markdown)

The `inlineMarkdown` method converts GitHub flavored Markdown into inline HTML using [CommonMark](https://commonmark.thephpleague.com/). However, unlike the `markdown` method, it does not wrap all generated HTML in a block-level element:

```php
use Illuminate\Support\Str;
$html = Str::of('**Laravel**')->inlineMarkdown();
// <strong>Laravel</strong>
```

**Markdown Security**

By default, Markdown supports raw HTML, which will expose Cross-Site Scripting (XSS) vulnerabilities when used with raw user input. As per the [CommonMark Security documentation](https://commonmark.thephpleague.com/security/), you may use the `html_input` option to either escape or strip raw HTML, and the `allow_unsafe_links` option to specify whether to allow unsafe links. If you need to allow some raw HTML, you should pass your compiled Markdown through an HTML Purifier:

```php
use Illuminate\Support\Str;
Str::of('Inject: <script>alert("Hello XSS!");</script>')->inlineMarkdown([    'html_input' => 'strip',    'allow_unsafe_links' => false,]);
// Inject: alert(&quot;Hello XSS!&quot;);
```

[**`is`**](strings.md#method-fluent-str-is)

The `is` method determines if a given string matches a given pattern. Asterisks may be used as wildcard values

```
use Illuminate\Support\Str;
$matches = Str::of('foobar')->is('foo*');
// true
$matches = Str::of('foobar')->is('baz*');
// false
```

[**`isAscii`**](strings.md#method-fluent-str-is-ascii)

The `isAscii` method determines if a given string is an ASCII string:

```php
use Illuminate\Support\Str;
$result = Str::of('Taylor')->isAscii();
// true
$result = Str::of('ü')->isAscii();
// false
```

[**`isEmpty`**](strings.md#method-fluent-str-is-empty)

The `isEmpty` method determines if the given string is empty:

```php
use Illuminate\Support\Str;
$result = Str::of('  ')->trim()->isEmpty();
// true
$result = Str::of('Laravel')->trim()->isEmpty();
// false
```

[**`isNotEmpty`**](strings.md#method-fluent-str-is-not-empty)

The `isNotEmpty` method determines if the given string is not empty:

```php
use Illuminate\Support\Str;
$result = Str::of('  ')->trim()->isNotEmpty();
// false
$result = Str::of('Laravel')->trim()->isNotEmpty();
// true
```

[**`isJson`**](strings.md#method-fluent-str-is-json)

The `isJson` method determines if a given string is valid JSON:

```php
use Illuminate\Support\Str;
$result = Str::of('[1,2,3]')->isJson();
// true
$result = Str::of('{"first": "John", "last": "Doe"}')->isJson();
// true
$result = Str::of('{first: "John", last: "Doe"}')->isJson();
// false
```

[**`isUlid`**](strings.md#method-fluent-str-is-ulid)

The `isUlid` method determines if a given string is a ULID:

```php
use Illuminate\Support\Str;
$result = Str::of('01gd6r360bp37zj17nxb55yv40')->isUlid();
// true
$result = Str::of('Taylor')->isUlid();
// false
```

[**`isUrl`**](strings.md#method-fluent-str-is-url)

The `isUrl` method determines if a given string is a URL:

```php
use Illuminate\Support\Str;
$result = Str::of('http://example.com')->isUrl();
// true
$result = Str::of('Taylor')->isUrl();
// false
```

The `isUrl` method considers a wide range of protocols as valid. However, you may specify the protocols that should be considered valid by providing them to the `isUrl` method:

```php
$result = Str::of('http://example.com')->isUrl(['http', 'https']);
```

[**`isUuid`**](strings.md#method-fluent-str-is-uuid)

The `isUuid` method determines if a given string is a UUID:

```php
use Illuminate\Support\Str;
$result = Str::of('5ace9ab9-e9cf-4ec6-a19d-5881212a452c')->isUuid();
// true
$result = Str::of('Taylor')->isUuid();
// false
```

[**`kebab`**](strings.md#method-fluent-str-kebab)

The `kebab` method converts the given string to `kebab-case`:

```php
use Illuminate\Support\Str;
$converted = Str::of('fooBar')->kebab();
// foo-bar
```

[**`lcfirst`**](strings.md#method-fluent-str-lcfirst)

The `lcfirst` method returns the given string with the first character lowercased:

```php
use Illuminate\Support\Str;
$string = Str::of('Foo Bar')->lcfirst();
// foo Bar
```

[**`length`**](strings.md#method-fluent-str-length)

The `length` method returns the length of the given string:

```php
use Illuminate\Support\Str;
$length = Str::of('Laravel')->length();
// 7
```

[**`limit`**](strings.md#method-fluent-str-limit)

The `limit` method truncates the given string to the specified length:

```php
use Illuminate\Support\Str;
$truncated = Str::of('The quick brown fox jumps over the lazy dog')->limit(20);
// The quick brown fox...
```

You may also pass a second argument to change the string that will be appended to the end of the truncated string:

```php
$truncated = Str::of('The quick brown fox jumps over the lazy dog')->limit(20, ' (...)');
// The quick brown fox (...)
```

If you would like to preserve complete words when truncating the string, you may utilize the `preserveWords` argument. When this argument is `true`, the string will be truncated to the nearest complete word boundary:

```php
$truncated = Str::of('The quick brown fox')->limit(12, preserveWords: true);
// The quick...
```

[**`lower`**](strings.md#method-fluent-str-lower)

The `lower` method converts the given string to lowercase:

```php
use Illuminate\Support\Str;
$result = Str::of('LARAVEL')->lower();
// 'laravel'
```

[**`markdown`**](strings.md#method-fluent-str-markdown)

The `markdown` method converts GitHub flavored Markdown into HTML:

```php
use Illuminate\Support\Str;
$html = Str::of('# Laravel')->markdown();
// <h1>Laravel</h1>
$html = Str::of('# Taylor <b>Otwell</b>')->markdown([    'html_input' => 'strip',]);
// <h1>Taylor Otwell</h1>
```

**Markdown Security**

By default, Markdown supports raw HTML, which will expose Cross-Site Scripting (XSS) vulnerabilities when used with raw user input. As per the [CommonMark Security documentation](https://commonmark.thephpleague.com/security/), you may use the `html_input` option to either escape or strip raw HTML, and the `allow_unsafe_links` option to specify whether to allow unsafe links. If you need to allow some raw HTML, you should pass your compiled Markdown through an HTML Purifier:

```php
use Illuminate\Support\Str;
Str::of('Inject: <script>alert("Hello XSS!");</script>')->markdown([    'html_input' => 'strip',    'allow_unsafe_links' => false,]);
// <p>Inject: alert(&quot;Hello XSS!&quot;);</p>
```

[**`mask`**](strings.md#method-fluent-str-mask)

The `mask` method masks a portion of a string with a repeated character, and may be used to obfuscate segments of strings such as email addresses and phone numbers:

```php
use Illuminate\Support\Str;
$string = Str::of('taylor@example.com')->mask('*', 3);
// tay***************
```

If needed, you may provide negative numbers as the third or fourth argument to the `mask` method, which will instruct the method to begin masking at the given distance from the end of the string:

```php
$string = Str::of('taylor@example.com')->mask('*', -15, 3);
// tay***@example.com
$string = Str::of('taylor@example.com')->mask('*', 4, -4);
// tayl**********.com
```

[**`match`**](strings.md#method-fluent-str-match)

The `match` method will return the portion of a string that matches a given regular expression pattern:

```php
use Illuminate\Support\Str;
$result = Str::of('foo bar')->match('/bar/');
// 'bar'
$result = Str::of('foo bar')->match('/foo (.*)/');
// 'bar'
```

[**`matchAll`**](strings.md#method-fluent-str-match-all)

The `matchAll` method will return a collection containing the portions of a string that match a given regular expression pattern:

```php
use Illuminate\Support\Str;
$result = Str::of('bar foo bar')->matchAll('/bar/');
// collect(['bar', 'bar'])
```

If you specify a matching group within the expression, Laravel will return a collection of the first matching group's matches:

```php
use Illuminate\Support\Str;
$result = Str::of('bar fun bar fly')->matchAll('/f(\w*)/');
// collect(['un', 'ly']);
```

If no matches are found, an empty collection will be returned.

[**`isMatch`**](strings.md#method-fluent-str-is-match)

The `isMatch` method will return `true` if the string matches a given regular expression:

```php
use Illuminate\Support\Str;
$result = Str::of('foo bar')->isMatch('/foo (.*)/');
// true
$result = Str::of('laravel')->isMatch('/foo (.*)/');
// false
```

[**`newLine`**](strings.md#method-fluent-str-new-line)

The `newLine` method appends an "end of line" character to a string:

```php
use Illuminate\Support\Str;
$padded = Str::of('Laravel')->newLine()->append('Framework');
// 'Laravel//  Framework'
```

[**`padBoth`**](strings.md#method-fluent-str-padboth)

The `padBoth` method wraps PHP's `str_pad` function, padding both sides of a string with another string until the final string reaches the desired length:

```php
use Illuminate\Support\Str;
$padded = Str::of('James')->padBoth(10, '_');
// '__James___'
$padded = Str::of('James')->padBoth(10);
// '  James   '
```

[**`padLeft`**](strings.md#method-fluent-str-padleft)

The `padLeft` method wraps PHP's `str_pad` function, padding the left side of a string with another string until the final string reaches the desired length:

```php
use Illuminate\Support\Str;
$padded = Str::of('James')->padLeft(10, '-=');
// '-=-=-James'
$padded = Str::of('James')->padLeft(10);
// '     James'
```

[**`padRight`**](strings.md#method-fluent-str-padright)

The `padRight` method wraps PHP's `str_pad` function, padding the right side of a string with another string until the final string reaches the desired length:

```php
use Illuminate\Support\Str;
$padded = Str::of('James')->padRight(10, '-');
// 'James-----'
$padded = Str::of('James')->padRight(10);
// 'James     '
```

[**`pipe`**](strings.md#method-fluent-str-pipe)

The `pipe` method allows you to transform the string by passing its current value to the given callable:

```php
use Illuminate\Support\Str;use Illuminate\Support\Stringable;
$hash = Str::of('Laravel')->pipe('md5')->prepend('Checksum: ');
// 'Checksum: a5c95b86291ea299fcbe64458ed12702'
$closure = Str::of('foo')->pipe(function (Stringable $str) {    return 'bar';});
// 'bar'
```

[**`plural`**](strings.md#method-fluent-str-plural)

The `plural` method converts a singular word string to its plural form. This function supports [any of the languages support by Laravel's pluralizer](../foundation/strings.md/localization/#pluralization-language):

```php
use Illuminate\Support\Str;
$plural = Str::of('car')->plural();
// cars
$plural = Str::of('child')->plural();
// children
```

You may provide an integer as a second argument to the function to retrieve the singular or plural form of the string:

```php
use Illuminate\Support\Str;
$plural = Str::of('child')->plural(2);
// children
$plural = Str::of('child')->plural(1);
// child
```

[**`position`**](strings.md#method-fluent-str-position)

The `position` method returns the position of the first occurrence of a substring in a string. If the substring does not exist within the string, `false` is returned:

```php
use Illuminate\Support\Str;
$position = Str::of('Hello, World!')->position('Hello');
// 0
$position = Str::of('Hello, World!')->position('W');
// 7
```

[**`prepend`**](strings.md#method-fluent-str-prepend)

The `prepend` method prepends the given values onto the string:

```php
use Illuminate\Support\Str;
$string = Str::of('Framework')->prepend('Laravel ');
// Laravel Framework
```

[**`remove`**](strings.md#method-fluent-str-remove)

The `remove` method removes the given value or array of values from the string:

```php
use Illuminate\Support\Str;
$string = Str::of('Arkansas is quite beautiful!')->remove('quite');
// Arkansas is beautiful!
```

You may also pass `false` as a second parameter to ignore case when removing strings.

[**`repeat`**](strings.md#method-fluent-str-repeat)

The `repeat` method repeats the given string:

```php
use Illuminate\Support\Str;
$repeated = Str::of('a')->repeat(5);
// aaaaa
```

[**`replace`**](strings.md#method-fluent-str-replace)

The `replace` method replaces a given string within the string:

```php
use Illuminate\Support\Str;
$replaced = Str::of('Laravel 6.x')->replace('6.x', '7.x');
// Laravel 7.x
```

The `replace` method also accepts a `caseSensitive` argument. By default, the `replace` method is case sensitive:

```php
$replaced = Str::of('macOS 13.x')->replace(    'macOS', 'iOS', caseSensitive: false);
```

[**`replaceArray`**](strings.md#method-fluent-str-replace-array)

The `replaceArray` method replaces a given value in the string sequentially using an array:

```php
use Illuminate\Support\Str;
$string = 'The event will take place between ? and ?';
$replaced = Str::of($string)->replaceArray('?', ['8:30', '9:00']);
// The event will take place between 8:30 and 9:00
```

[**`replaceFirst`**](strings.md#method-fluent-str-replace-first)

The `replaceFirst` method replaces the first occurrence of a given value in a string:

```php
use Illuminate\Support\Str;
$replaced = Str::of('the quick brown fox jumps over the lazy dog')->replaceFirst('the', 'a');
// a quick brown fox jumps over the lazy dog
```

[**`replaceLast`**](strings.md#method-fluent-str-replace-last)

The `replaceLast` method replaces the last occurrence of a given value in a string:

```php
use Illuminate\Support\Str;
$replaced = Str::of('the quick brown fox jumps over the lazy dog')->replaceLast('the', 'a');
// the quick brown fox jumps over a lazy dog
```

[**`replaceMatches`**](strings.md#method-fluent-str-replace-matches)

The `replaceMatches` method replaces all portions of a string matching a pattern with the given replacement string:

```php
use Illuminate\Support\Str;
$replaced = Str::of('(+1) 501-555-1000')->replaceMatches('/[^A-Za-z0-9]++/', '')
// '15015551000'
```

The `replaceMatches` method also accepts a closure that will be invoked with each portion of the string matching the given pattern, allowing you to perform the replacement logic within the closure and return the replaced value:

```php
use Illuminate\Support\Str;
$replaced = Str::of('123')->replaceMatches('/\d/', function (array $matches) {    return '['.$matches[0].']';});
// '[1][2][3]'
```

[**`replaceStart`**](strings.md#method-fluent-str-replace-start)

The `replaceStart` method replaces the first occurrence of the given value only if the value appears at the start of the string:

```php
use Illuminate\Support\Str;
$replaced = Str::of('Hello World')->replaceStart('Hello', 'Laravel');
// Laravel World
$replaced = Str::of('Hello World')->replaceStart('World', 'Laravel');
// Hello World
```

[**`replaceEnd`**](strings.md#method-fluent-str-replace-end)

The `replaceEnd` method replaces the last occurrence of the given value only if the value appears at the end of the string:

```php
use Illuminate\Support\Str;
$replaced = Str::of('Hello World')->replaceEnd('World', 'Laravel');
// Hello Laravel
$replaced = Str::of('Hello World')->replaceEnd('Hello', 'Laravel');
// Hello World
```

[**`scan`**](strings.md#method-fluent-str-scan)

The `scan` method parses input from a string into a collection according to a format supported by the [`sscanf` PHP function](https://www.php.net/manual/en/function.sscanf.php):

```php
use Illuminate\Support\Str;
$collection = Str::of('filename.jpg')->scan('%[^.].%s');
// collect(['filename', 'jpg'])
```

[**`singular`**](strings.md#method-fluent-str-singular)

The `singular` method converts a string to its singular form. This function supports [any of the languages support by Laravel's pluralizer](../foundation/strings.md/localization/#pluralization-language):

```php
use Illuminate\Support\Str;
$singular = Str::of('cars')->singular();
// car
$singular = Str::of('children')->singular();
// child
```

[**`slug`**](strings.md#method-fluent-str-slug)

The `slug` method generates a URL friendly "slug" from the given string:

```php
use Illuminate\Support\Str;
$slug = Str::of('Laravel Framework')->slug('-');
// laravel-framework
```

[**`snake`**](strings.md#method-fluent-str-snake)

The `snake` method converts the given string to `snake_case`:

```php
use Illuminate\Support\Str;
$converted = Str::of('fooBar')->snake();
// foo_bar
```

[**`split`**](strings.md#method-fluent-str-split)

The `split` method splits a string into a collection using a regular expression:

```php
use Illuminate\Support\Str;
$segments = Str::of('one, two, three')->split('/[\s,]+/');
// collect(["one", "two", "three"])
```

[**`squish`**](strings.md#method-fluent-str-squish)

The `squish` method removes all extraneous white space from a string, including extraneous white space between words:

```php
use Illuminate\Support\Str;
$string = Str::of('    laravel    framework    ')->squish();
// laravel framework
```

[**`start`**](strings.md#method-fluent-str-start)

The `start` method adds a single instance of the given value to a string if it does not already start with that value:

```php
use Illuminate\Support\Str;
$adjusted = Str::of('this/string')->start('/');
// /this/string
$adjusted = Str::of('/this/string')->start('/');
// /this/string
```

[**`startsWith`**](strings.md#method-fluent-str-starts-with)

The `startsWith` method determines if the given string begins with the given value:

```php
use Illuminate\Support\Str;
$result = Str::of('This is my name')->startsWith('This');
// true
```

[**`stripTags`**](strings.md#method-fluent-str-strip-tags)

The `stripTags` method removes all HTML and PHP tags from a string:

```php
use Illuminate\Support\Str;
$result = Str::of('<a href="https://laravel.com">Taylor <b>Otwell</b></a>')->stripTags();
// Taylor Otwell
$result = Str::of('<a href="https://laravel.com">Taylor <b>Otwell</b></a>')->stripTags('<b>');
// Taylor <b>Otwell</b>
```

[**`studly`**](strings.md#method-fluent-str-studly)

The `studly` method converts the given string to `StudlyCase`:

```php
use Illuminate\Support\Str;
$converted = Str::of('foo_bar')->studly();
// FooBar
```

[**`substr`**](strings.md#method-fluent-str-substr)

The `substr` method returns the portion of the string specified by the given start and length parameters:

```php
use Illuminate\Support\Str;
$string = Str::of('Laravel Framework')->substr(8);
// Framework
$string = Str::of('Laravel Framework')->substr(8, 5);
// Frame
```

[**`substrReplace`**](strings.md#method-fluent-str-substrreplace)

The `substrReplace` method replaces text within a portion of a string, starting at the position specified by the second argument and replacing the number of characters specified by the third argument. Passing `0` to the method's third argument will insert the string at the specified position without replacing any of the existing characters in the string:

```php
use Illuminate\Support\Str;
$string = Str::of('1300')->substrReplace(':', 2);
// 13:
$string = Str::of('The Framework')->substrReplace(' Laravel', 3, 0);
// The Laravel Framework
```

[**`swap`**](strings.md#method-fluent-str-swap)

The `swap` method replaces multiple values in the string using PHP's `strtr` function:

```php
use Illuminate\Support\Str;
$string = Str::of('Tacos are great!')    ->swap([        'Tacos' => 'Burritos',        'great' => 'fantastic',    ]);
// Burritos are fantastic!
```

[**`take`**](strings.md#method-fluent-str-take)

The `take` method returns a specified number of characters from the beginning of the string:

```php
use Illuminate\Support\Str;
$taken = Str::of('Build something amazing!')->take(5);
// Build
```

[**`tap`**](strings.md#method-fluent-str-tap)

The `tap` method passes the string to the given closure, allowing you to examine and interact with the string while not affecting the string itself. The original string is returned by the `tap` method regardless of what is returned by the closure:

```php
use Illuminate\Support\Str;use Illuminate\Support\Stringable;
$string = Str::of('Laravel')    ->append(' Framework')    ->tap(function (Stringable $string) {        dump('String after append: '.$string);    })    ->upper();
// LARAVEL FRAMEWORK
```

[**`test`**](strings.md#method-fluent-str-test)

The `test` method determines if a string matches the given regular expression pattern:

```php
use Illuminate\Support\Str;
$result = Str::of('Laravel Framework')->test('/Laravel/');
// true
```

[**`title`**](strings.md#method-fluent-str-title)

The `title` method converts the given string to `Title Case`:

```php
use Illuminate\Support\Str;
$converted = Str::of('a nice title uses the correct case')->title();
// A Nice Title Uses The Correct Case
```

[**`toBase64`**](strings.md#method-fluent-str-to-base64)

The `toBase64` method converts the given string to Base64:

```php
use Illuminate\Support\Str;
$base64 = Str::of('Laravel')->toBase64();
// TGFyYXZlbA==
```

[**`toHtmlString`**](strings.md#method-fluent-str-to-html-string)

The `toHtmlString` method converts the given string to an instance of `Illuminate\Support\HtmlString`, which will not be escaped when rendered in Blade templates:

```php
use Illuminate\Support\Str;
$htmlString = Str::of('Nuno Maduro')->toHtmlString();
```

[**`transliterate`**](strings.md#method-fluent-str-transliterate)

The `transliterate` method will attempt to convert a given string into its closest ASCII representation:

```php
use Illuminate\Support\Str;
$email = Str::of('ⓣⓔⓢⓣ@ⓛⓐⓡⓐⓥⓔⓛ.ⓒⓞⓜ')->transliterate()
// 'test@laravel.com'
```

[**`trim`**](strings.md#method-fluent-str-trim)

The `trim` method trims the given string. Unlike PHP's native `trim` function, Laravel's `trim` method also removes unicode whitespace characters:

```php
use Illuminate\Support\Str;
$string = Str::of('  Laravel  ')->trim();
// 'Laravel'
$string = Str::of('/Laravel/')->trim('/');
// 'Laravel'
```

[**`ltrim`**](strings.md#method-fluent-str-ltrim)

The `ltrim` method trims the left side of the string. Unlike PHP's native `ltrim` function, Laravel's `ltrim` method also removes unicode whitespace characters:

```php
use Illuminate\Support\Str;
$string = Str::of('  Laravel  ')->ltrim();
// 'Laravel  '
$string = Str::of('/Laravel/')->ltrim('/');
// 'Laravel/'
```

[**`rtrim`**](strings.md#method-fluent-str-rtrim)

The `rtrim` method trims the right side of the given string. Unlike PHP's native `rtrim` function, Laravel's `rtrim` method also removes unicode whitespace characters:

```php
use Illuminate\Support\Str;
$string = Str::of('  Laravel  ')->rtrim();
// '  Laravel'
$string = Str::of('/Laravel/')->rtrim('/');
// '/Laravel'
```

[**`ucfirst`**](strings.md#method-fluent-str-ucfirst)

The `ucfirst` method returns the given string with the first character capitalized:

```php
use Illuminate\Support\Str;
$string = Str::of('foo bar')->ucfirst();
// Foo bar
```

[**`ucsplit`**](strings.md#method-fluent-str-ucsplit)

The `ucsplit` method splits the given string into a collection by uppercase characters:

```php
use Illuminate\Support\Str;
$string = Str::of('Foo Bar')->ucsplit();
// collect(['Foo', 'Bar'])
```

[**`unwrap`**](strings.md#method-fluent-str-unwrap)

The `unwrap` method removes the specified strings from the beginning and end of a given string:

```php
use Illuminate\Support\Str;
Str::of('-Laravel-')->unwrap('-');
// Laravel
Str::of('{framework: "Laravel"}')->unwrap('{', '}');
// framework: "Laravel"
```

[**`upper`**](strings.md#method-fluent-str-upper)

The `upper` method converts the given string to uppercase:

```php
use Illuminate\Support\Str;
$adjusted = Str::of('laravel')->upper();
// LARAVEL
```

[**`when`**](strings.md#method-fluent-str-when)

The `when` method invokes the given closure if a given condition is `true`. The closure will receive the fluent string instance:

```php
use Illuminate\Support\Str;use Illuminate\Support\Stringable;
$string = Str::of('Taylor')->when(true, function (Stringable $string) {
return $string->append(' Otwell');
});
// 'Taylor Otwell'
```

If necessary, you may pass another closure as the third parameter to the `when` method. This closure will execute if the condition parameter evaluates to `false`.

[**`whenContains`**](strings.md#method-fluent-str-when-contains)

The `whenContains` method invokes the given closure if the string contains the given value. The closure will receive the fluent string instance:

```php
use Illuminate\Support\Str;use Illuminate\Support\Stringable;
$string = Str::of('tony stark')            ->whenContains('tony', function (Stringable $string) {                return $string->title();            });
// 'Tony Stark'
```

If necessary, you may pass another closure as the third parameter to the `when` method. This closure will execute if the string does not contain the given value.

You may also pass an array of values to determine if the given string contains any of the values in the array:

```php
use Illuminate\Support\Str;use Illuminate\Support\Stringable;
$string = Str::of('tony stark')            ->whenContains(['tony', 'hulk'], function (Stringable $string) {                return $string->title();            });
// Tony Stark
```

[**`whenContainsAll`**](strings.md#method-fluent-str-when-contains-all)

The `whenContainsAll` method invokes the given closure if the string contains all of the given sub-strings. The closure will receive the fluent string instance:

```php
use Illuminate\Support\Str;use Illuminate\Support\Stringable;
$string = Str::of('tony stark')->whenContainsAll(['tony', 'stark'], function (Stringable $string) {
return $string->title();                });
// 'Tony Stark'
```

If necessary, you may pass another closure as the third parameter to the `when` method. This closure will execute if the condition parameter evaluates to `false`.

[**`whenEmpty`**](strings.md#method-fluent-str-when-empty)

The `whenEmpty` method invokes the given closure if the string is empty. If the closure returns a value, that value will also be returned by the `whenEmpty` method. If the closure does not return a value, the fluent string instance will be returned:

```php
use Illuminate\Support\Str;use Illuminate\Support\Stringable;
$string = Str::of('  ')->whenEmpty(function (Stringable $string) {    return $string->trim()->prepend('Laravel');});
// 'Laravel'
```

[**`whenNotEmpty`**](strings.md#method-fluent-str-when-not-empty)

The `whenNotEmpty` method invokes the given closure if the string is not empty. If the closure returns a value, that value will also be returned by the `whenNotEmpty` method. If the closure does not return a value, the fluent string instance will be returned:

```php
use Illuminate\Support\Str;use Illuminate\Support\Stringable;
$string = Str::of('Framework')->whenNotEmpty(function (Stringable $string) {    return $string->prepend('Laravel ');});
// 'Laravel Framework'
```

[**`whenStartsWith`**](strings.md#method-fluent-str-when-starts-with)

The `whenStartsWith` method invokes the given closure if the string starts with the given sub-string. The closure will receive the fluent string instance:

```php
use Illuminate\Support\Str;use Illuminate\Support\Stringable;
$string = Str::of('disney world')->whenStartsWith('disney', function (Stringable $string) {    return $string->title();});
// 'Disney World'
```

[**`whenEndsWith`**](strings.md#method-fluent-str-when-ends-with)

The `whenEndsWith` method invokes the given closure if the string ends with the given sub-string. The closure will receive the fluent string instance:

```php
use Illuminate\Support\Str;use Illuminate\Support\Stringable;
$string = Str::of('disney world')->whenEndsWith('world', function (Stringable $string) {    return $string->title();});
// 'Disney World'
```

[**`whenExactly`**](strings.md#method-fluent-str-when-exactly)

The `whenExactly` method invokes the given closure if the string exactly matches the given string. The closure will receive the fluent string instance:

```php
use Illuminate\Support\Str;use Illuminate\Support\Stringable;
$string = Str::of('laravel')->whenExactly('laravel', function (Stringable $string) {    return $string->title();});
// 'Laravel'
```

[**`whenNotExactly`**](strings.md#method-fluent-str-when-not-exactly)

The `whenNotExactly` method invokes the given closure if the string does not exactly match the given string. The closure will receive the fluent string instance:

```php
use Illuminate\Support\Str;use Illuminate\Support\Stringable;
$string = Str::of('framework')->whenNotExactly('laravel', function (Stringable $string) {    return $string->title();});
// 'Framework'
```

[**`whenIs`**](strings.md#method-fluent-str-when-is)

The `whenIs` method invokes the given closure if the string matches a given pattern. Asterisks may be used as wildcard values. The closure will receive the fluent string instance:

```php
use Illuminate\Support\Str;use Illuminate\Support\Stringable;
$string = Str::of('foo/bar')->whenIs('foo/*', function (Stringable $string) {    return $string->append('/baz');});
// 'foo/bar/baz'
```

[**`whenIsAscii`**](strings.md#method-fluent-str-when-is-ascii)

The `whenIsAscii` method invokes the given closure if the string is 7 bit ASCII. The closure will receive the fluent string instance:

```php
use Illuminate\Support\Str;use Illuminate\Support\Stringable;
$string = Str::of('laravel')->whenIsAscii(function (Stringable $string) {    return $string->title();});
// 'Laravel'
```

[**`whenIsUlid`**](strings.md#method-fluent-str-when-is-ulid)

The `whenIsUlid` method invokes the given closure if the string is a valid ULID. The closure will receive the fluent string instance:

```php
use Illuminate\Support\Str;
$string = Str::of('01gd6r360bp37zj17nxb55yv40')->whenIsUlid(function (Stringable $string) {    return $string->substr(0, 8);});
// '01gd6r36'
```

[**`whenIsUuid`**](strings.md#method-fluent-str-when-is-uuid)

The `whenIsUuid` method invokes the given closure if the string is a valid UUID. The closure will receive the fluent string instance:

```php
use Illuminate\Support\Str;use Illuminate\Support\Stringable;
$string = Str::of('a0a2a2d2-0b87-4a18-83f2-2529882be2de')->whenIsUuid(function (Stringable $string) {    return $string->substr(0, 8);});
// 'a0a2a2d2'
```

[**`whenTest`**](strings.md#method-fluent-str-when-test)

The `whenTest` method invokes the given closure if the string matches the given regular expression. The closure will receive the fluent string instance:

```php
use Illuminate\Support\Str;use Illuminate\Support\Stringable;
$string = Str::of('laravel framework')->whenTest('/laravel/', function (Stringable $string) {    return $string->title();});
// 'Laravel Framework'
```

[**`wordCount`**](strings.md#method-fluent-str-word-count)

The `wordCount` method returns the number of words that a string contains:

```php
use Illuminate\Support\Str;
Str::of('Hello, world!')->wordCount(); // 2
```

[**`words`**](strings.md#method-fluent-str-words)

The `words` method limits the number of words in a string. If necessary, you may specify an additional string that will be appended to the truncated string:

{% code overflow="wrap" %}
```
use Illuminate\Support\Str;
 
$string = Str::of('Perfectly balanced, as all things should be.')->words(3, ' >>>');
 
// Perfectly balanced, as >>>
```
{% endcode %}

[**`wrap`**](strings.md#method-fluent-str-wrap)

The `wrap` method wraps the given string with an additional string or pair of strings:

```php
use Illuminate\Support\Str;
 
Str::of('Laravel')->wrap('"');
 
// "Laravel"
 
Str::is('is')->wrap(before: 'This ', after: ' Laravel!');
 
// This is Laravel!
```
