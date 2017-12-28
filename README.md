# PHP Coding Standards

PSR-1/2/4/5/12 are a solid foundation, but are not an entire coding style by themselves.

This guide goes well-beyond brace placement and tabs vs. spaces to cover topics such as docblock annotations, ternary operations and which variation of English to use. It aims for thoroughness and pedanticism over hoping that we can all get along.

* [PSR-1] — Basic Coding Style
* [PSR-2] — Coding Style Guide
* [PSR-4] — Autoloading Patterns
* [PSR-5] — Documentation Block Patterns
* [PSR-12] — Extended Coding Style
* [Symfony] — Additional Standards.

## Enforced by Code

I have reduced these written-word guidelines to only specify what I cannot enforce using existing linters. Here are the linter rules which should be used by [PHP Code Sniffer] and [PHP CS Fixer].

* [phpcs.xml](https://github.com/simplepie/simplepie-ng/blob/master/phpcs.xml)
* [.php_cs.dist](https://github.com/simplepie/simplepie-ng/blob/master/.php_cs.dist)

These can (and should, often) be run to fix coding style errors.

```bash
make lint
```

## Guidelines

### Naming Things

* Constants are always `ALL_CAPS`.

* Abstract classes should be called `Abstract{Name}`.

* Interfaces should be called `{Name}Interface`.

* Traits should be called `{Name}Trait`.

* Namespaces, classes, traits, interfaces, etc., should all prefer singular names.

  ```php
  MyCode\Mixin\ResponseHandler
  MyCode\Mixin\TableFormatter
  MyCode\Util\DataGenerator
  ```

* There's no hard and fast rule when it comes to the length of a name, so just try and be as concise as possible without affecting clarity too much.

* According to PSR-4, a class called `MyCode` should be in a file called `MyCode.php`.

### Constants

* Global constants are bad.

* Class constants are good.

* Enum-like class constants are better.

### Strings

* Single quotes most of the time.

* `sprintf()` is the preferred form for injecting variables into strings.

* For string interpolation (e.g., with HEREDOC), use the `{$variable}` format. Do NOT use `${variable}` or `$variable`.

* NOWDOC strings are preferred over HEREDOC strings.

* Use NOWDOC/HEREDOC for multi-line strings.

### Ternary Statements

* Don't test if the statement is `false`. That becomes confusing fast.

* Preferred formatting is:

  ```php
  $condition
      ? true
      : false;
  ```

* Use `??` when possible.

  ```php
  return $data[0] ?? null;
  ```

### Comments

* Non-documentation comments are strongly encouraged.

* A general rule of thumb is that if you look at a section of code and think "Wow, I don't want to try and describe that", you <del>need to comment it</del> should refactor it before you forget how it works.

* C-style comments (`/* */`) and standard C++ comments (`//`) are both fine. However, single-line comments should opt for `//`, while multi-line comments should opt for `/* */`.

* For readability, add a single space after `//` style comments, and an extra space immediately inside both ends of a `/* */`-style comment.

### DocBlocks

1. Follows the [PSR-5](http://j.mp/psr-5) (draft) pattern.

1. Any _short-hand_ refrences to software licenses should use the [SPDX identifier](https://spdx.org/licenses/).

1. Data types (if they are classes) can either be fully-qualified, or can match a valid namespace alias.

   ```php
   /**
    * [getSomeKindOfData() description]
    * 
    * @param  string           $string [description]
    * @param  SimpleXMLElement $xml    [description]
    * @return [type]                   [description]
    * 
    * @throws [Exception class]
    */
   public static function getSomeKindOfData($string, SimpleXMLElement $xml) {
       // ...
   }
   ```

1. Leveraging return types (PHP 7.0+) is the preferred approach for informing IDEs about which classes we're working with.

   ```php
   use Symfony\Components\EventDispatcher\EventDispatcher;
   
   public function getDispatcher(): EventDispatcher
   {
       return $this->dispatcher;
   }
   ```

### Spelling

If there is ever a discrepancy between English-speaking dialects, use **U.S. English** as a baseline for both spelling and word choice. [Grammarist](http://grammarist.com/spelling/) and similar websites can help ensure intended usage.

```
color (correct)
colour (incorrect)

spelled (correct)
spelt (incorrect)

canceled (correct)
cancelled (incorrect)

labeled (correct)
labelled (incorrect)

math (correct)
maths (incorrect)

apartment (correct)
flat (incorrect)

"Apple is very successful." (correct)
"Apple are very successful." (incorrect)
```

### CLI

* When writing CLI scripts, don't presume to know where the PHP binary is installed. Use the `env` binary to pick-up from the local environment.

  ```bash
  #! /usr/bin/env php
  ```

### PHP_EOL

* Rather than using `\n` or `\r\n` as forced line breaks in your files, use the `PHP_EOL` constant instead.

* PHP will use whichever end-of-line character is most appropriate for the platform that it's currently running on.

### Blacklisted

Never use the following features of PHP. The world will come to an end if you do.

* [`extract()`](http://php.net/extract)
* [`eval()`](http://php.net/eval)
* [`GOTO`](http://php.net/goto)

### Miscellaneous

* No global variables. (ಠ_ಠ)

* Code must not produce any warnings or errors when PHP's error reporting level is set to `error_reporting(-1)`. ([Source](https://twitter.com/rasmus/status/7448448829))

* You are encouraged to give increment/decrement operators (`++` and `--`) a line of their own (with the exception of `for` loops).

  ```php
  $foo[$i++] = $j; // Discouraged: relies on $i being incremented after the expression is evaluated
  $foo[--$j] = $i; // Discouraged: relies on $j being decremented before the expression is evaluated

  $foo[$i] = $j;
  $i++;            // Encouraged: obvious when $i is incremented

  $j--;
  $foo[$j] = $i;   // Encouraged: obvious when $j is decremented
  ```

## License
My intention is to release all rights to this documentation and make it available under the Public Domain. Unfortunately, in the U.S. it's not quite that cut-and-dry. So, I am dual-licensing this work under [CC0](LICENSE-CC0) and the [Unlicense](LICENSE-UNLICENSE). You can choose whichever license you would prefer to adhere to.

<p xmlns:dct="http://purl.org/dc/terms/" xmlns:vcard="http://www.w3.org/2001/vcard-rdf/3.0#">
  <a rel="license"
     href="http://creativecommons.org/publicdomain/zero/1.0/">
    <img src="http://i.creativecommons.org/p/zero/1.0/88x31.png" style="border-style: none;" alt="CC0" />
  </a>
  <br />
  To the extent possible under law,
  <a rel="dct:publisher"
     href="https://github.com/skyzyx/php-coding-standards">
    <span property="dct:title">Ryan Parman</span></a>
  has waived all copyright and related or neighboring rights to
  "<span property="dct:title">Parman PHP Coding Standards</span>".
This work is published from:
<span property="vcard:Country" datatype="dct:ISO3166"
      content="US" about="https://github.com/skyzyx/php-coding-standards">
  United States</span>.
</p>

  [PSR-1]: http://www.php-fig.org/psr/psr-1/
  [PSR-2]: http://www.php-fig.org/psr/psr-2/
  [PSR-4]: http://www.php-fig.org/psr/psr-4/
  [PSR-5]: https://github.com/phpDocumentor/fig-standards/blob/master/proposed/phpdoc.md
  [PSR-12]: https://github.com/php-fig/fig-standards/blob/master/proposed/extended-coding-style-guide.md
  [Symfony]: https://symfony.com/doc/current/contributing/code/standards.html
  [PHP Code Sniffer]: https://github.com/squizlabs/PHP_CodeSniffer
  [PHP CS Fixer]: http://cs.sensiolabs.org
