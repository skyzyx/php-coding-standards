# Grammar

* Global variables
    * No. ಠ_ಠ
    * If you are using `$_GLOBALS`, you have a pattern problem.

* Code must not produce any warnings or errors when PHP's error reporting level is set to `error_reporting(-1)`. ([Source](https://twitter.com/rasmus/status/7448448829))

* PHP-only files should have an opening `<?php` tag, but should not have a closing tag! Adding a closing PHP tag can occasionally cause strange issues when importing. As such, leave out the closing `?>` tag.

* Do not use short open tags (`<?`) for files which are entirely PHP.

* All control structures use braces, even if they’re optional, for files which are entirely PHP.

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

## View/Template Intermingling

View/Template-layer code (code which intermingles PHP with HTML/non-PHP) allows the following exceptions:

* Template echoes (`<?=`) are OK.

* Short-open tags (`<?`) may be used to wrap control structures.

  ```php
  <? if (condition): ?>
    <tag>View-layer code.</tag>
  <? endif ?>
  ```

* `if`, `for`, `foreach`, `while`, and similar kinds of blocks use the `:` character to begin their statements.

  ```php
  <? if (condition): ?>
  ```

* `endif`, `endfor`, `endforeach`, `endwhile`, and similar kinds of blocks do NOT use a trailing `;` character.

  ```php
  <? endif ?>
  ```

* All `<? ... ?>` blocks have a single space just inside the open/close tokens.

  ```php
  <? if (condition): ?>
    <?= $variable ?>
  <? endif ?>
  ```

## Arrays

* "New" array syntax should be used.

* For multi-line arrays, the use of a trailing comma for the last item in the array is encouraged. This minimizes the impact of adding new items on successive lines, and helps to ensure no parse errors occur due to a missing comma.

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

* If any array elements have their own line, they all should. Avoid inconsistency where some are on the same line and others are not.

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

* For simple string interpolation with double-quoted strings, use the `{$variable}` format. Do NOT use `${variable}` or `$variable`.

* For complex string interpolation, always use `sprintf()`.

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

* In conditions, the value should be on the left and the variable should be on the right. ([Supporting evidence](https://www.securecoding.cert.org/confluence/display/c/VOID+EXP21-C.+Place+constants+on+the+left+of+equality+comparisons))

  ```php
  // Encouraged
  if ('abc' === $abc) {}

  // Discouraged
  if ($abc === 'abc') {}
  ```

## `==` or `===`

* If you are comparing against an absolute value (e.g., a string, integer, boolean), always use `===`.

* If you are comparing against a _truthy_ or _falsey_ value, always use `==`.
