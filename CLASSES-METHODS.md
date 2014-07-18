# Classes and Methods

## Type Hinting

* Type-hint whenever possible

* If you're thinking of supporting `mixed`, ask yourself why. Challenge yourself and your presumptions to determine if you _really_ need to accept a `mixed`.

## Long Lists of Parameters

* It can be difficult to remember the order of parameters once the list becomes longer than 3 or 4. If some parameters are required and some are optional (or if some parameters can be made optional), consider keeping the required parameters required, and passing all optional parameters as an associative array at the end.

## Class calls

* When instantiating a class, always use parentheses -- even when they're optional.

  ```php
  // Good
  $feed = new MyClass();

  // Bad
  $feed = new MyClass;
  ```
