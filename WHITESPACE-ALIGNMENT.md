# Whitespace and Alignment

* You are encouraged to give increment/decrement operators (`++` and `--`) a line of their own (with the exception of `for` loops).

  ```php
  $foo[$i++] = $j; // Discouraged: relies on $i being incremented after the expression is evaluated
  $foo[--$j] = $i; // Discouraged: relies on $j being decremented before the expression is evaluated

  $foo[$i] = $j;
  $i++;            // Encouraged: obvious when $i is incremented

  $j--;
  $foo[$j] = $i;   // Encouraged: obvious when $j is decremented
  ```
