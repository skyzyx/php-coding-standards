# PSR Recommendations

* [PSR-0](http://www.php-fig.org/psr/psr-0/)

* [PSR-1](http://www.php-fig.org/psr/psr-1/)

* [PSR-2](http://www.php-fig.org/psr/psr-2/), with the following exceptions:
    * Braces follow the [Uncompressed Style](DEFINE-BRACES.md).
    * Template code (intermingling PHP with HTML) is permitted to use the short-open tag (i.e., `<?`).
    * Line lengths have a HARD LIMIT of 120 characters. (Better than 80, but still not ridiculous.)
    * Extra line breaks are encouraged for readability.

* [PSR-5 Draft](https://github.com/phpDocumentor/fig-standards/blob/master/proposed/phpdoc.md) for DocBlocks.


## Summary of PSR-1/2 Recommendations

The key words "MUST", "MUST NOT", "REQUIRED", "SHALL", "SHALL NOT", "SHOULD", "SHOULD NOT", "RECOMMENDED", "MAY", and "OPTIONAL" in this document are to be interpreted as described in [RFC 2119](http://tools.ietf.org/html/rfc2119).

* PHP-only files MUST use only the `<?php` tag.

* Files MUST use only UTF-8 without BOM for PHP code.

* Files SHOULD either declare symbols (classes, functions, constants, etc.) or cause side-effects (e.g. generate output, change `.ini` settings, etc.) but SHOULD NOT do both.

* Namespaces and classes MUST follow PSR-0.

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
