# PSR Recommendations

* [PSR-1](http://www.php-fig.org/psr/psr-1/), with the following exceptions:
    * Template code (intermingling PHP with HTML) MAY use the short-open tag (i.e., `<?`) if it has been enabled. \[[#](https://github.com/php-fig/fig-standards/blob/master/accepted/PSR-1-basic-coding-standard.md#21-php-tags)\]

* [PSR-2](http://www.php-fig.org/psr/psr-2/), with the following exceptions:
    * Line lengths have a HARD LIMIT of 120 characters. \[[#](https://github.com/php-fig/fig-standards/blob/master/accepted/PSR-2-coding-style-guide.md#23-lines)\] 
    * Closures MAY (but are not REQUIRED to) be declared with a space after the `function` keyword. White space for defining Closures SHOULD follow the same rules as when defining methods and functions. \[[#](https://github.com/php-fig/fig-standards/blob/master/accepted/PSR-2-coding-style-guide.md#6-closures)\] 
    * The opening brace for a Closure MAY go on the next line following the `function` keyword. White space for defining Closures SHOULD follow the same rules as when defining methods and functions. \[[#](https://github.com/php-fig/fig-standards/blob/master/accepted/PSR-2-coding-style-guide.md#6-closures)\] 

* [PSR-4](http://www.php-fig.org/psr/psr-4/) for autoloading.

* [PSR-5 Draft](https://github.com/phpDocumentor/fig-standards/blob/master/proposed/phpdoc.md) for DocBlocks.

* [PSR-12 Draft](https://github.com/php-fig/fig-standards/blob/master/proposed/extended-coding-style-guide.md), with the following exceptions:
    * \[Clarification\] Each individual Trait that is imported into a class MUST be included one-per-line, and each inclusion MUST have its own `use` statement. This matches the PSR-2 format for including Namespaces and Namespace Aliases. \[[#](https://github.com/php-fig/fig-standards/blob/master/proposed/extended-coding-style-guide.md#42-using-traits)\]
    * When including Namespaces, Traits, Constants and Functions, the `use` statements SHOULD be in alphabetical order, except when a different order makes more sense in the present context (e.g., `ClassOne`, `ClassTwo`, `ClassThree`, `ClassFour`). This is PSR-2-compatible. \[[#](https://github.com/php-fig/fig-standards/blob/master/proposed/extended-coding-style-guide.md#3-declare-statements-namespace-and-use-declarations)\]
    * You SHOULD use `use` statements for classes in the root namespace. `use Exception; throw new Exception();` is preferred over `throw new \Exception();`. \[[#](https://github.com/php-fig/fig-standards/blob/master/proposed/extended-coding-style-guide.md#3-declare-statements-namespace-and-use-declarations)\]
    * For Anonymous Classes, the opening bracket SHOULD be placed on the line immediately following the `class` keyword. This matches the PSR-2 format for how classes are defined. \[[#](https://github.com/php-fig/fig-standards/blob/master/proposed/extended-coding-style-guide.md#8-anonymous-classes)\]


## Summary of PSR-1/2/12 Recommendations

The key words "MUST", "MUST NOT", "REQUIRED", "SHALL", "SHALL NOT", "SHOULD", "SHOULD NOT", "RECOMMENDED", "MAY", and "OPTIONAL" in this document are to be interpreted as described in [RFC 2119](http://tools.ietf.org/html/rfc2119).

* PHP-only files MUST use only the `<?php` tag.

* Files MUST use only UTF-8 without BOM for PHP code.

* Files SHOULD either declare symbols (classes, functions, constants, etc.) or cause side-effects (e.g. generate output, change `.ini` settings, etc.) but SHOULD NOT do both.

* Namespaces and classes MUST follow PSR-4.

* Class names MUST be declared in `StudlyCaps`.

  ```php
  class MyClass {}
  ```

* Class constants MUST be declared in all upper case with underscore separators.

  ```php
  class MyClass
  {
      const BOMB_DIGGITY = true;
  }
  ```

* Method names MUST be declared in `camelCase`.

  ```php
  public function putThatThingBackWhereItCameFromOrSoHelpMe() {}
  ```

* Code MUST use 4 spaces for indenting, not tabs.

* There MUST be one blank line after the `namespace` declaration, and there MUST be one blank line after the block of
  `use` declarations.

  ```php
  namespace MyCode\Api\Cars;

  use \Exception;
  use MyCode\Engine\Chevrolet;

  class Create {}
  ```

* Visibility must be declared on all properties and methods.
  * `abstract` and `final` must be declared before the visibility. (See [PHP: Class Abstraction](http://www.php.net/manual/en/language.oop5.abstract.php))
  * `static` must be declared after the visibility. (See [PHP: Static Keyword](http://www.php.net/manual/en/language.oop5.static.php))

    ```php
    abstract class MyClass {}
    final class MyClass {}

    abstract public function MyMethod() {}
    final public function MyMethod() {}
    abstract public static function MyMethod() {}
    ```

* Control structure keywords MUST have one space after them; method and function calls MUST NOT.

  ```php
  if () {}
  else () {}
  public function example() {}
  ```

* Opening parentheses for control structures MUST NOT have a space after them, and closing parentheses for control structures MUST NOT have a space before.

  ```php
  if ('abc' === $abc) {}
  ```

* Unused `use` statements must be removed.

* All items of the `@param` phpdoc tags must be aligned vertically.

  ```php
  /**
   * Formats a single-level response.
   *
   * @param  Response        $response Guzzle response object.
   * @param  OutputInterface $output   Symfony Console output.
   * @return void
   */
  public static function handleResponse(Response $response, OutputInterface $output) {}
  ```

* An empty line feed should precede a return statement.

* Remove trailing whitespace at the end of lines.

* The keyword `elseif` should be used instead of `else if` so that all control keywords looks like single words.

* A file must always end with an empty line feed.
