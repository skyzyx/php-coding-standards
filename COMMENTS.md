# Comments

* Non-documentation comments are strongly encouraged. A general rule of thumb is that if you look at a section of code and think "Wow, I don't want to try and describe that", you need to comment it before you forget how it works.

* C-style comments (`/* */`) and standard C++ comments (`//`) are both fine.

* For readability, add a single space after `//` style comments, and an extra space immediately inside both ends of a `/* */`-style comment.

* Use of Perl/shell style comments (`#`) is discouraged.

  ```php
  // Encouraged Comment
  /* Encouraged Comment */

  # Discouraged Comment
  //Discouraged Comment
  /*Discouraged Comment*/
  ```

* If you are making a longer, multi-line comment, use line breaks instead of spaces immediately inside both ends of a `/* */`-style comment. The content may, at your option, be indented as well.

  ```php
  /*
      This is an extra long comment that I'm breaking up
      into multiple lines for improved readability.
  */
  ```

* There should always be one line of whitespace above the start of a comment block.

  ```php
  // This is my code.
  echo 'This is my code.';

  // This is more code.
  echo 'This is more code.';

  if (condition) {

      // comment
      echo 'code';
  }
  ```
