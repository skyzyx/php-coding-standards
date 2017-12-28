# Language Patterns and Best Practices

## CLI

* When writing CLI scripts, don't presume to know where the PHP binary is installed. Use the `env` binary to pick-up from the local environment.

  ```bash
  #! /usr/bin/env php
  ```

## Constants

* Global constants are bad.

* Class constants are good.

* Enum-like class constants are better.

## PHP_EOL

* Rather than using `\n` or `\r\n` as forced line breaks in your files, use the `PHP_EOL` constant instead.

* PHP will use whichever end-of-line character is most appropriate for the platform that it's currently running on.

## Blacklisted

Never use the following features of PHP. The world will come to an end if you do.

* [`extract()`](http://php.net/extract)
* [`eval()`](http://php.net/eval)
* [`GOTO`](http://php.net/goto)
