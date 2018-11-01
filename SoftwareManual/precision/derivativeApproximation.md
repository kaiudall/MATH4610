# Math 4610 Fundamentals of Computational Mathematics

**Routine Name:**           derivApprox

**Author:** Kai Udall

**Language:** Python 3.6.4

**Description/Purpose:** This routine will compute the approximate value of the derivative of a single variable function, using the limit definition of a derivative's approximate version. (f(x+h)-f(x)

**Input:** This routine takes a function, an x value, and an h value.

**Output:** This routine returns a float of the derivative approximation for the given function at its user designated x value.

**Usage/Example:**

The routine has three arguments needed to return the numeric derivative approximation.

      def f(x):
          return x**2
      
      derivApprox(f, 1, 0.01)

Output from the line above:

      2.0100000000000007

2.0100 is an approximate value for the correct value of the derivative of x^2 evalued at x=1.

**Implementation/Code:** The following is the code for derivApprox()

      def derivApprox(function, x, h):
          return (function(x+h)-function(x))/h
