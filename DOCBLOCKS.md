# DocBlocks

## Methods

1. Follows the [PSR-5](http://j.mp/psr-5) (draft) pattern.

1. Data types (if they are classes) can either be fully-qualified, or can match a valid namespace alias.

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

## `return`

Leveraging return types (PHP 7.0+) is the preferred approach for informing IDEs about which classes we're working with.

```php
use Symfony\Components\EventDispatcher\EventDispatcher;

public function getDispatcher(): EventDispatcher
{
    return $this->dispatcher;
}
```

Old-style annotations (below) are only acceptable for PHP 5.x codebases.

```php
public function getDispatcher()
{
    /** @var \Symfony\Components\EventDispatcher\EventDispatcher */
    return $this->dispatcher;
}
```

## Licenses

Any _short-hand_ refrences to software licenses should use the [SPDX identifier](https://spdx.org/licenses/).
