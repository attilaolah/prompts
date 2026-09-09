# Sparse Binary Expansion

Implement an efficient way of enumerating numbers that can be aded to left-shifted copies of themselves to forme a
binary repdigit.

The trivial example are the Mersenne numbers themselves: e.g. the binary 11 can be added to 1100 to form 1111, which
itself is a Mersenne number:

```
    11
+ 1100
------
= 1111
```

We can also inject an arbitrary number of zeros:

```
   101
+ 1010
------
= 1111
```

```
    1001001
+  10010010
+ 100100100
-----------
= 111111111
```

More generally, we can inject an arbitrary number of runs of k zeros between runs of k ones. E.g. for k=2 (runs of two
zeros and two ones), we get the following sum rom "duplicating" the digits of the above example:

```
      11000011000011
+   1100001100001100
+ 110000110000110000
--------------------
= 111111111111111111
```

## Part 1

Your task is to construct these numbers in an efficient way. Enumerating all integers and then checking whether they
satisfy the constraint is a no-go: that would be too slow. Your solution must run in constant time.

It is _not_ a requirement for the numbers to be generated in strictly ascending order, however, they should be
generated in ascending bit length.

Use Python 3.14+. Write a function with this signature:

```python
from collections.abc import Generator


def generate() -> Generator[tuple[int, int, int]]:
    """Generate numbers satisfying the sparse binary expansion rule.

    Yields:
        Tuples of (n, bit_length, sum_bit_length)
    """
```

## Part 2

(Will be provided once Part 1 has been completed).

Extend Part 1 with additional numbers not covered by the rules above. For example, 1011001 (89) can be summed using
carry bits (displayed in parenthesis below).

Your solution must still be O(1). Only include additional rules that can be implemented in constant time.

```
(  11111     )
      1011001
+    10110010
+   101100100
+ 10110010000
-------------
= 11111111111
```

Use any a type-safe compiled language.
