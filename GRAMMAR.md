# Grammar

* No global variables. ಠ_ಠ

* Code must not produce any warnings or errors when PHP's error reporting level is set to `error_reporting(-1)`. ([Source](https://twitter.com/rasmus/status/7448448829))

## Strings

* Single quotes most of the time.

* `sprintf()` is the preferred form for injecting variables into strings.

* For string interpolation (e.g., with HEREDOC), use the `{$variable}` format. Do NOT use `${variable}` or `$variable`.

* NOWDOC strings are preferred over HEREDOC strings.

* Use NOWDOC/HEREDOC for multi-line strings.

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
