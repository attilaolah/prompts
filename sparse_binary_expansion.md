# Sparse Binary Expansion

Implement an efficient way of enumerating numbers that can be aded to left-shifted copies of themselves to forme a
binary repdigit.

The trivial example are the Mersenne numbers themselves: e.g. the binary 11 can be added to 1100 to form 1111, which
itself is a Mersenne number:

    11
+ 1100
------
= 1111

We can also inject an arbitrary number of zeros:

   101
+ 1010
------
= 1111

    1001001
+  10010010
+ 100100100
-----------
= 111111111

More generally, we can inject an arbitrary number of runs of k zeros between runs of k ones. E.g. for k=2 (runs of two
zeros and two ones), we get the following sum rom "duplicating" the digits of the above example:

      11000011000011
+   1100001100001100
+ 110000110000110000
--------------------
= 111111111111111111

Your task is to construct these numbers in an efficient way. Enumerating all integers and then checking whether they
satisfy the constraint is a no-go: that would be too slow. Your solution must run in constant time.

It is *not* a requirement for the numbers to be generated in strictly ascending order, however, they should be
generated in ascending bit length.

Use Python.
