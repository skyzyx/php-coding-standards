# Language Patterns and Best Practices

## CLI

* When writing CLI scripts, don't presume to know where the PHP binary is installed. Use the `env` binary to pick-up from the local environment.

  ```bash
  #! /usr/bin/env php
  ```

## Language constructs

* `echo`, `require`, `include`, `print` should not use parentheses for invokation.

## Regular Expressions

* Using [PCRE regular expressions](http://www.php.net_manual/en/book.pcre.php) (e.g., `preg_*`) instead of their POSIX counterparts (e.g., `ereg_*`). _(Removed in newer versions of PHP.)_

## Constants

* Global constants are bad.

* Class constants are good.

* Enum-like class constants are better.

## Visibility

* Methods should always define their visibility (e.g. `public`, `private`, `protected`) first, then whether or not they are `static`.

* `protected` (and `public`) methods and properties should _not_ use an underscore prefix, as was common in PHP 4-era code.

## Type Casting/Juggling

* Sometimes, an object response can be _stringy_ or _array-y_. Make sure you typecast into a true string or array if you're not sure (e.g., `SimpleXMLElement`, `stdClass`).

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

This can be leveraged in some very useful ways. If you don't know how this works, you should read-up on this pattern and understand it's not always a typo.

## Error Suppression

* Do not use the `@` operator for error supression. It has a _high_ performance cost, and can cause inexplicable errors when used incorrectly.

* Avoid the need to use this by ensuring that you've properly checked values all along the way to avoid errors in the first place (see PHP: [Error Control Operators](http://www.php.net/manual/en/language.operators.errorcontrol.php)).

## PHP_EOL

* Rather than using `\n` or `\r\n` as forced line breaks in your files, use the `PHP_EOL` constant instead.

* PHP will use whichever end-of-line character is most appropriate for the platform that it's currently running on.

## Blacklisted

Never use the following features of PHP. The world will come to an end if you do.

* [`extract()`](http://php.net/extract)
* [`eval()`](http://php.net/eval)
* [`GOTO`](http://php.net/goto)
