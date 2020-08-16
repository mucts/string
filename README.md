<p align="center"><img src="https://images.mucts.com/image/exp_def_white.png" width="400"></p>
<p align="center">
    <a href="https://scrutinizer-ci.com/g/mucts/string"><img src="https://scrutinizer-ci.com/g/mucts/string/badges/build.png" alt="Build Status"></a>
    <a href="https://scrutinizer-ci.com/g/mucts/string"><img src="https://scrutinizer-ci.com/g/mucts/string/badges/code-intelligence.svg" alt="Code Intelligence Status"></a>
    <a href="https://scrutinizer-ci.com/g/mucts/string"><img src="https://scrutinizer-ci.com/g/mucts/string/badges/quality-score.png" alt="Scrutinizer Code Quality"></a>
    <a href="https://packagist.org/packages/mucts/string"><img src="https://poser.pugx.org/mucts/string/d/total.svg" alt="Total Downloads"></a>
    <a href="https://packagist.org/packages/mucts/string"><img src="https://poser.pugx.org/mucts/string/v/stable.svg" alt="Latest Stable Version"></a>
    <a href="https://packagist.org/packages/mucts/string"><img src="https://poser.pugx.org/mucts/string/license.svg" alt="License"></a>
</p>

# Str 字符串#

> `Str`类提供一个便捷的操作字符串的封装。

# 使用

- `Str::camel`

> 将给定字符串「蛇式」转化为 `camelCase`「驼峰式」

```php
use MuCTS\String\Str;

$converted = Str::camel('foo_bar');
// fooBar
```

- `Str::endsWith`

> 函数判断指定的字符串是否以给定的值结尾

```php
use MuCTS\String\Str;

$result = Str::endsWith('This is my name', 'name');
// true
```

- `Str::kebab`

> 将给定的「驼峰式」字符串转化为`kebab-case`「短横式」字符串

```php
use MuCTS\String\Str;

$converted = Str::kebab('fooBar');
// foo-bar
```

- `Str::snake`

> `Str::snake` 函数将给定的字符串转换为 `snake_case`「蛇式」

```php
use MuCTS\String\Str;

$converted = Str::snake('fooBar');
// foo_bar
```

- `Str::startsWith`

> `Str::startsWith` 函数判断给定的字符串的开头是否是指定值

```php
use MuCTS\String\Str;

$result = Str::startsWith('This is my name', 'This');
// true
```

- `Str::after`

> `Str::after` 函数返回在字符串中指定值之后的所有内容

```php
use MuCTS\String\Str;

$slice = Str::after('This is my name', 'This is');
// ' my name'
```

- `Str::before`

> `Str::before` 函数返回在字符串中指定值之前的所有内容

```php
use MuCTS\String\Str;

$slice = Str::before('This is my name', 'my name');
// 'This is '
```

- `Str::contains`

> `Str::contains` 函数判断给定的字符串是否包含给定的值（区分大小写）

```php
use MuCTS\String\Str;

$contains = Str::contains('This is my name', 'my');

// true
```

- `Str::finish`

> `Str::finish` 函数将给定的字符串以给定的值结尾返回（如果它尚未以给定值结尾）

```php
use MuCTS\String\Str;

$adjusted = Str::finish('this/string', '/');
// this/string/
$adjusted = Str::finish('this/string/', '/');
// this/string/
```

- `Str::is`

> `Str::is` 函数判断给定的字符串是否匹配给定的模式。星号 * 可以用来表示通配符

```php
use MuCTS\String\Str;
$matches = Str::is('foo*', 'foobar');
// true
$matches = Str::is('baz*', 'foobar');
// false
```

- `Str::limit`

> `Str::limit` 函数按给定的长度截断给定的字符串

```php
use MuCTS\String\Str;
$truncated = Str::limit('The quick brown fox jumps over the lazy dog', 20);
// The quick brown fox...
```

> 你也可以传递第三个参数来改变将被追加到最后的字符串：

```php
use MuCTS\String\Str;
$truncated = Str::limit('The quick brown fox jumps over the lazy dog', 20, ' (...)');
// The quick brown fox (...)
```
- `Str::orderedUuid`

> `Str::orderedUuid` 方法高效生成一个可存储在索引数据库列中的「第一时间」 `UUID`

```php
use MuCTS\String\Str;
return (string) Str::orderedUuid();
```

- `Str::plural`

> `Str::plural` 函数将字符串转换为复数形式。该函数目前仅支持英文

```php
use MuCTS\String\Str;
$plural = Str::plural('car');
// cars
$plural = Str::plural('child');
// children
```

> 你可以提供一个整数作为函数的第二个参数来检索字符串的单数或复数形式

```php
use MuCTS\String\Str;
$plural = Str::plural('child', 2);
// children
$plural = Str::plural('child', 1);
// child
```

- `Str::random`

> `Str::random` 函数生成一个指定长度的随机字符串。这个函数用 `PHP` 的 `random_bytes` 函数

```php
use MuCTS\String\Str;
$random = Str::random(40);
```

- `Str::replaceArray`

> `Str::replaceArray` 函数使用数组顺序替换字符串中的给定值

```php
use MuCTS\String\Str;
$string = 'The event will take place between ? and ?';
$replaced = Str::replaceArray('?', ['8:30', '9:00'], $string);
// The event will take place between 8:30 and 9:00
```

- `Str::replaceFirst`

> `Str::replaceFirst` 函数替换字符串中给定值的第一个匹配项

```php
use MuCTS\String\Str;

$replaced = Str::replaceFirst('the', 'a', 'the quick brown fox jumps over the lazy dog');
// a quick brown fox jumps over the lazy dog
```

`Str::replaceLast`

> `Str::replaceLast` 函数替换字符串中最后一次出现的给定值：

```php
use MuCTS\String\Str;

$replaced = Str::replaceLast('the', 'a', 'the quick brown fox jumps over the lazy dog');
// the quick brown fox jumps over a lazy dog
```
- `Str::singular`

> `Str::singular` 函数将字符串转换为单数形式。该函数目前仅支持英文

```php
use MuCTS\String\Str;

$singular = Str::singular('cars');
// car
$singular = Str::singular('children');
// child
```
- `Str::slug`

> `Str::slug` 函数将给定的字符串生成一个 `URL` 友好的 「`slug`」

```php
use MuCTS\String\Str;

$slug = Str::slug('Laravel 5 Framework', '-');
// laravel-5-framework
```

- `Str::start`

> `Str::start` 函数将给定值添加到给定字符串的开始位置（如果字符串尚未以给定值开始）

```php
use MuCTS\String\Str;

$adjusted = Str::start('this/string', '/');
// /this/string

$adjusted = Str::start('/this/string', '/');
// /this/string
```

- `Str::studly`

> `Str::studly` 函数将给定的字符串转换为 「变种驼峰命名」

```php
use MuCTS\String\Str;

$converted = Str::studly('foo_bar');
// FooBar
```

- `Str::title`

> `Str::title` 函数将给定的字符串转换为「首字母大写」

```php
use MuCTS\String\Str;

$converted = Str::title('a nice title uses the correct case');
// A Nice Title Uses The Correct Case
```

- `Str::uuid`

> `Str::uuid` 方法生成一个 `UUID`（版本 4）

```php
use MuCTS\String\Str;

return (string) Str::uuid();
```
