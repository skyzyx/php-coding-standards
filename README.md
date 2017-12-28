# Parman PHP Coding Standards

PSR-1/2/4/5/12 are a solid foundation, but are not an entire coding style by themselves. I have taken the time to document all of the nitpicky patterns and nuances of my personal coding style.

It goes well-beyond brace placement and tabs vs. spaces to cover topics such as docblock annotations, ternary operations and which variation of English to use. It aims for thoroughness and pedanticism over hoping that we can all get along.

* [PSR-1] — Basic Coding Style
* [PSR-2] — Coding Style Guide
* [PSR-4] — Autoloading Patterns
* [PSR-5] — Documentation Block Patterns
* [PSR-12] — Extended Coding Style
* [Symfony] — Additional Standards.

## Enforced by Code

I have reduced these guidelines to only specify what I cannot enforce using existing linters. Here are the linter rules which should be used by [PHP Code Sniffer] and [PHP CS Fixer].

* [phpcs.xml](https://github.com/simplepie/simplepie-ng/blob/master/phpcs.xml)
* [.php_cs.dist](https://github.com/simplepie/simplepie-ng/blob/master/.php_cs.dist)

## Disclaimer

This is an attempt to document my personal coding style, patterns, and rationale. This is NOT an attempt to tell anybody else how to write code. There is a 100% chance that someone will disagree with me, and that's perfectly OK. This is for me.

If you want to fork this and make edits for yourself or your team, please go right ahead.

## License
My intention is to release all rights to this documentation and make it available under the Public Domain. Unfortunately, in the U.S. it's not quite that cut-and-dry. So, I am dual-licensing this work under [CC0](LICENSE-CC0) and the [Unlicense](LICENSE-UNLICENSE). You can choose whichever license you would prefer to adhere to.

<p xmlns:dct="http://purl.org/dc/terms/" xmlns:vcard="http://www.w3.org/2001/vcard-rdf/3.0#">
  <a rel="license"
     href="http://creativecommons.org/publicdomain/zero/1.0/">
    <img src="http://i.creativecommons.org/p/zero/1.0/88x31.png" style="border-style: none;" alt="CC0" />
  </a>
  <br />
  To the extent possible under law,
  <a rel="dct:publisher"
     href="https://github.com/skyzyx/php-coding-standards">
    <span property="dct:title">Ryan Parman</span></a>
  has waived all copyright and related or neighboring rights to
  "<span property="dct:title">Parman PHP Coding Standards</span>".
This work is published from:
<span property="vcard:Country" datatype="dct:ISO3166"
      content="US" about="https://github.com/skyzyx/php-coding-standards">
  United States</span>.
</p>

  [PSR-1]: http://www.php-fig.org/psr/psr-1/
  [PSR-2]: http://www.php-fig.org/psr/psr-2/
  [PSR-4]: http://www.php-fig.org/psr/psr-4/
  [PSR-5]: https://github.com/phpDocumentor/fig-standards/blob/master/proposed/phpdoc.md
  [PSR-12]: https://github.com/php-fig/fig-standards/blob/master/proposed/extended-coding-style-guide.md
  [Symfony]: https://symfony.com/doc/current/contributing/code/standards.html
  [PHP Code Sniffer]: https://github.com/squizlabs/PHP_CodeSniffer
  [PHP CS Fixer]: http://cs.sensiolabs.org
