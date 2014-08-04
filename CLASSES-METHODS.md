# Classes and Methods

## Using Namespaced Classes

* For any external classes being used in the current class, you should `use` them between the namespace declaration and the class declaration.

* All `use` statements should be sorted alphanumerically.

  ```php
  namespace Foo\Bar;

  use \Exception;
  use \SimpleXMLElement;
  use Fuzz\Buzz\BazzTrait;

  class Baz {}
  ```

* In the `use` statement, globally-accessible classes MUST be prefixed with the `\` character, as per PHP's namespace resolution rules. However, all namespaced _userland_ classes should NOT be prefixed with the `\` character, as per the [PHP Manual](http://php.net/manual/en/language.namespaces.importing.php) (emphasis **mine**).

  > Note that for namespaced names (fully qualified namespace names containing namespace separator, such as Foo\Bar as opposed to global names that do not, such as FooBar), **the leading backslash is unnecessary and not recommended**, as import names must be fully qualified, and are not processed relative to the current namespace.

## Using Traits

* Traits should be referenced with `use` first-thing inside the class declaration.

  ```php
  class Baz
  {
      use BazzTrait;

      // Class code...
  }
  ```

## Type Hinting

* Type-hint method parameters whenever possible

* If you're thinking of supporting `mixed`, ask yourself why. Challenge yourself and your presumptions to determine if you _really_ need to accept a `mixed`.

## Long Lists of Parameters

* It can be difficult to remember the order of parameters once the list becomes longer than 3 or 4. If some parameters are required and some are optional (or if some parameters can be made optional), consider keeping the required parameters required, and passing all optional parameters as an associative array at the end.

* Alternatively, and probably better, is to break a method down into smaller methods. It may be trying to do too much.

## Class calls

* When instantiating a class, always use parentheses -- even when they're optional.

  ```php
  // Good
  $feed = new MyClass();

  // Bad
  $feed = new MyClass;
  ```

* Since all external classes (and, optionally, namespaces) being used in the current class have been aliased with `use` (see above), you always reference classes with short-form naming.

  ```php
  use Foo\Bar\Baz;
  use Foo\Middleware as MW;
  
  class Example
  {
      $baz = new Baz(new MW\MyMiddleware());
  }
  ```
