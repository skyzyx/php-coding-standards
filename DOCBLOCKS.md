# DocBlocks

## Methods

1. Follows the [PSR-5](http://j.mp/psr-5) (draft) pattern.

2. Types, parameters and descriptions should all be _vertically_ aligned.

3. Data types (if they are classes) can either be fully-qualified, or can match a valid namespace alias.

4. Native types should use the full name (e.g., `integer`, `string`, `boolean`).

```
/**
 * [getSomeKindOfData() description]
 * 
 * @param   string           $string [description]
 * @param   SimpleXMLElement $xml    [description]
 * @returns [type]                   [description]
 * 
 * @throws [Exception class]
 */
public static function getSomeKindOfData($string, SimpleXMLElement $xml) {
    // ...
}
```
