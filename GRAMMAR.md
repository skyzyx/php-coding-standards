# Grammar

* Global variables.
    * No. ಠ_ಠ
    * If you are using `$_GLOBALS`, you have a pattern problem.

* Code must not produce any warnings or errors when PHP's error reporting level is set to `error_reporting(-1)`. ([Source](https://twitter.com/rasmus/status/7448448829))

## Strings

* Single quotes most of the time

* For simple string interpolation with double-quoted strings, use the `{$variable}` format. Do NOT use `${variable}` or `$variable`.

* For complex string interpolation, always use `sprintf()`.

* Use HEREDOC or NOWDOC syntax for multi-line strings.

## Ternary statements

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
