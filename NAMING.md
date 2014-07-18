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

* There's no hard and fast rule when it comes to the length of a name, so just try and be as concise as possible without affecting clarity too much.

* According to PSR-0/4, a class called `MyCode` should be in a file called `MyCode.php`.
