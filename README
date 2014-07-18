# PSR Recommendations

* [PSR-0](http://www.php-fig.org/psr/psr-0/)
    * This _replaces_ the previous standard for using PSR-4 (which doesn't actually apply to anybody except for
      library vendors.)
* [PSR-1](http://www.php-fig.org/psr/psr-1/)
* [PSR-2](http://www.php-fig.org/psr/psr-2/), with the following exceptions:
    * Opening braces (i.e., `{`), and closing braces (i.e., `}`), are always on their own line. (Studies have shown this
      enhances readability.)
    * Line lengths have a HARD LIMIT of 120 characters. (Better than 80, but still not ridiculous.)
    * Extra line breaks are encouraged for readability.
* [PSR-5 Draft](https://github.com/phpDocumentor/fig-standards/blob/master/proposed/phpdoc.md) for DocBlocks.


## Summary of PSR-1/2 Recommendations

The key words "MUST", "MUST NOT", "REQUIRED", "SHALL", "SHALL NOT", "SHOULD", "SHOULD NOT", "RECOMMENDED", "MAY", and
"OPTIONAL" in this document are to be interpreted as described in [RFC 2119](http://tools.ietf.org/html/rfc2119).

* PHP-only files MUST use only the `<?php` tag.
* Template files containing HTML are allowed to use `<?` around control structures, and `<?=` for direct output. For example:

  ```html
  <? if (condition): ?>
      <tag>HTML block with <?= $variable ?>.</tag>
  <? endif ?>
  ```

* Files MUST use only UTF-8 without BOM for PHP code.
* Files SHOULD either declare symbols (classes, functions, constants, etc.) or cause side-effects (e.g. generate output,
  change .ini settings, etc.) but SHOULD NOT do both.
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
  namespace WePay\Api\Checkout;

  use \Exception;
  use WePay\MoneyEngine\Currency;

  class Create {}
  ```

* Visibility must be declared on all properties and methods.
  * `abstract` and `final` must be declared before the visibility.
    (See [PHP: Class Abstraction](http://www.php.net/manual/en/language.oop5.abstract.php))
  * `static` must be declared after the visibility.
    (See [PHP: Static Keyword](http://www.php.net/manual/en/language.oop5.static.php))

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

* Opening parentheses for control structures MUST NOT have a space after them, and closing parentheses for control
  structures MUST NOT have a space before.

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

----

# Editor Settings

* Line-endings should use the `\n` character (`LF`) used by default on Mac OS X and *nix systems.
    * Windows uses `\r\n` (`CRLF`) by default, so make sure that your IDE saves files with Unix-flavored line-endings.
* No trailing whitespace per line.
* A file must always end with an empty line feed.

----

# Grammar

* Global variables
    * No. ಠ_ಠ
    * If you are using `$_GLOBALS`, you have a pattern problem.
* Code must not produce any warnings or errors when PHP's error reporting level is set to `error_reporting(-1)`.
  ([Source](https://twitter.com/rasmus/status/7448448829))
* PHP-only files should have an opening `<?php` tag, but should not have a closing tag! Adding a closing PHP tag can
  occasionally cause strange issues when importing. As such, leave out the closing `?>` tag.
* Do not use short open tags (`<?`)
    * This is different from template echo (`<?=`), which is OK.
* All control structures use braces, even if they’re optional.

  ```php
  // Bad
  if (!is_null($args)) $abc = 'abc';

  // Bad
  if (!is_null($args))
      $abc = 'abc';

  // Good
  if (!is_null($args))
  {
      $abc = 'abc';
  }
  ```

## Arrays

* "New" array syntax should be used.
* For multi-line arrays, the use of a trailing comma for the last item in the array is encouraged. This minimizes
  the impact of adding new items on successive lines, and helps to ensure no parse errors occur due to a missing
  comma.

  ```php
  // Good
  $indexed_array = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10];

  // Good
  $months_english = [
      'January',
      'February',
      'March',
      'April',
      'May',
      'June',
      'July',
      'August',
      'September',
      'October',
      'November',
      'December',
  ];
  ```

* If any array elements have their own line, they all should. Avoid inconsistency where some are on the same line and
  others are not.

  ```php
  // Bad
  $associative_array = array('Key1' => 'Value',
                             'Key2' => 'Value',
                             'Key3' => 'Value');

  // Bad
  $associative_array = array('Key1' => 'Value',
      'Key2' => 'Value',
      'Key3' => 'Value');
  ```

## Strings

* Single quotes most of the time
* For string interpolation, always use `sprintf()`.
* Use HEREDOC syntax for multi-line strings.

## Ternary statements

* Don't test if the statement is `false`. That becomes confusing fast.

  ```php
  // Bad
  $value = !condition ? false : true;

  // Good
  $value = condition ? true : false;
  ```

* No more than a single condition should go into a ternary statement. Use a switch-case or if-else condition instead.
* In conditions, the value should be on the left and the variable should be on the right.
  ([Supporting evidence](https://www.securecoding.cert.org/confluence/display/seccode/EXP21-C.+Place+constants+on+the+left+of+equality+comparisons))

  ```php
  // Encouraged
  if ('abc' === $abc) {}

  // Discouraged
  if ($abc === 'abc') {}
  ```

## `==` or `===`

* If you are comparing against an absolute value (e.g., a string, integer, boolean), always use `===`.
* If you are comparing against a _truthy_ or _falsey_ value, always use `==`.

----

# Comments

* Non-documentation comments are strongly encouraged. A general rule of thumb is that if you look at a section of code
  and think "Wow, I don't want to try and describe that", you need to comment it before you forget how it works.
* C-style comments (`/* */`) and standard C++ comments (`_`) are both fine.
* For readability, add a single space after `_` style comments, and an extra space immediately inside both ends of a
  `/* */`-style comment.
* Use of Perl/shell style comments (`#`) is discouraged.

  ```php
  // Encouraged Comment
  /* Encouraged Comment */

  # Discouraged Comment
  //Discouraged Comment
  /*Discouraged Comment*/
  ```

* If you are making a longer, multi-line comment, use line breaks instead of spaces immediately inside both ends of a
  `/* */`-style comment. The content may, at your option, be indented as well.

  ```php
  /*
      This is an extra long comment that I'm breaking up
      into multiple lines for improved readability.
  */
  ```

----

# Whitespace and Alignment

* Follow _PSR Recommendations_ (above) by default.
* `switch` control statement:
    * In addition to the standard whitespace for `switch` statements, the contents of each `case` or `default` block
      should be indented for readability. This includes the closing `break`;.
    * Also, there should always be a `default` block.
* Blocks of variable setting should have all `=` characters vertically-aligned.
* Associative arrays (e.g., hashes, dictionaries) should have all `=>` symbols vertically-aligned.
* You are encouraged to give increment/decrement operators (`++` and `--`) a line of their own (with the exception of
  `for` loops).

  ```php
  $foo[$i++] = $j; // Discouraged: relies on $i being incremented after the expression is evaluated
  $foo[--$j] = $i; // Discouraged: relies on $j being decremented before the expression is evaluated

  $foo[$i] = $j;
  $i++;            // Encouraged: obvious when $i is incremented

  $j--;
  $foo[$j] = $i;   // Encouraged: obvious when $j is decremented
  ```

----

# Spelling

If there is ever a discrepancy between English-speaking dialects, use U.S. English as a baseline for both spelling and
word choice. [Grammarist](http://grammarist.com/spelling/) can help ensure correct spelling.

```
color (correct)
colour (incorrect)
```

Also:

```
spelled (correct)
spelt (incorrect)
```

----

# Naming

* Variables are `$snake_case`.
* Constants are always `ALL_CAPS`.
* Abstract classes should be called `Abstract{Name}`.
* Interfaces should be called `{Name}Interface`.
* Traits should be called `{Name}Trait`.
* Namespaces, classes, traits, interfaces, etc., should all prefer singular names.

  ```php
  MyCode\Mixin\ResponseHandler
  MyCode\Mixin\TableFormatter
  MyCode\Utility\DataGenerator
  ```

* There's no hard and fast rule when it comes to the length of a name, so just try and be as concise as possible without
  affecting clarity too much.
* According to PSR-0/4, a class called `MyCode` should be in a file called `MyCode.php`.
    * This implies one class per file -- as explicitly called-out in PSR-0.

----

# Classes and Methods

## Type Hinting

* Type-hint whenever possible
* If you're thinking of supporting `mixed`, ask yourself why. Challenge yourself and your presumptions to determine
  if you _really_ need to accept a `mixed`.

## Long Lists of Parameters

* It can be difficult to remember the order of parameters once the list becomes longer than 3 or 4. If some
  parameters are required and some are optional (or if some parameters can be made optional), consider keeping the
  required parameters required, and passing all optional parameters as an associative array at the end.

## Class calls

* When instantiating a class, always use parentheses -- even when they're optional.

  ```php
  // Good
  $feed = new MyClass();

  // Bad
  $feed = new MyClass;
  ```

----

# Language Patterns and Best Practices

## CLI

* When writing CLI scripts, don't presume to know where the PHP binary is installed. Use the `env` binary to pick-up
  from the local environment.

  ```bash
  #! /usr/bin/env php
  ```

## `use`

* All `use` statements are sorted alphabetically.
* As per the PHP Manual, `use` statements for namespaced classes should not be prefixed with a `\` character.
    * This excludes _global_ classes.

## Language constructs

* `echo`, `require`, `include`, `print` should not use parentheses.

## Regular Expressions

* Using [PCRE regular expressions](http://www.php.net_manual/en/book.pcre.php) (e.g., `preg_*`) instead of their POSIX
  counterparts (e.g., `ereg_*`). _(Removed in newer versions of PHP.)_

## Constants

* Global constants are bad.
* Class constants are good.
* Enum-like class constants are better.

## Visibility

* Methods should always define their visibility (e.g. `public`, `private`, `protected`) first, then whether or not they
  are `static`.
* The use of `private` class methods and properties should be avoided -- use `protected` instead, so that another class
  could extend your class and change the method if necessary.
* `protected` (and `public`) methods and properties should _not_ use an underscore prefix, as was common in PHP 4-era
  code.

## Type Casting/Juggling

* Sometimes, an object response can be _stringy_ or _array-y_. Make sure you typecast into a true string or array if
  you're not sure (e.g., `SimpleXMLElement`, `stdClass`).
* Typecasting should follow the same whitespace rules listed above, and use short words whenever possible.

  ```php
  // Encouraged
  (boolean) $result;
  (integer) $value;

  // Discouraged
  (bool) $result;
  ( bool ) $result;
  (bool)$result;
  (bool)  $result;
  (int) $value;
  ```

## Assignments in Conditionals

* It can be very confusing for developers who think you have a typo (i.e. they assume you meant `==`, when you
  intentionally meant `=`).
* Because of this, doing variable assignments as part of conditionals is discouraged. Instead, try this approach:

  ```php
  $time = strtotime('tomorrow, 9am')

  if ($time > time())
  {
      // code that uses $time...
  }
  ```

## Error Suppression

* Do not use the `@` operator for error supression.
* It has a high performance cost, and can cause inexplicable errors when used incorrectly.
* Avoid the need to use this by ensuring that you've properly checked values all along the way to avoid errors in the
  first place (see PHP: [Error Control Operators](http://www.php.net/manual/en/language.operators.errorcontrol.php)).

## PHP_EOL

* Rather than using `\n` or `\r\n` as forced line breaks in your files, use the `PHP_EOL` constant instead.
* PHP will use whichever end-of-line character is most appropriate for the platform that it's currently running on.

## Blacklisted

Never use the following features of PHP. The world will come to an end if you do.

* [`extract()`](http://php.net/extract)
* [`eval()`](http://php.net/eval)
* [`GOTO`](http://php.net/goto)
