# DocBlocks

## Methods

1. Follows the [PSR-5](http://j.mp/psr-5) (draft) pattern.

2. Types, parameters and descriptions should all be _vertically_ aligned.

3. Data types (if they are classes) can either be fully-qualified, or can match a valid namespace alias.

4. Native types should use the full name (e.g., `integer`, `string`, `boolean`).

```php
/**
 * [getSomeKindOfData() description]
 * 
 * @param  string           $string [description]
 * @param  SimpleXMLElement $xml    [description]
 * @return [type]                   [description]
 * 
 * @throws [Exception class]
 */
public static function getSomeKindOfData($string, SimpleXMLElement $xml) {
    // ...
}
```

## Properties

You can choose to annotate the properties with only the data type.

```php
/** @var integer */
protected $count = 0;

/** @var string[] */
private $array_of_strings = [];
```

## `return`

Type-hinting all `return` statements can enable better auto-complete functionality in non-IDE editors (e.g., Textmate, Sublime Text, Komodo). Type hinting here is the same as for properties, except that the type must be fully-qualified.

```php
/** @var \Symfony\Components\EventDispatcher\EventDispatcher */
return $dispatcher;
```
