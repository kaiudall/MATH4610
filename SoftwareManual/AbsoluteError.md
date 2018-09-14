# Math 4610 Fundamentals of Computational Mathematics

**Routine Name:**           Absolute Error

**Author:** Kai Udall

**Language:** Python 3.6.4

**Description/Purpose:** This routine will compute the absolute error of a given value, and its computational counterpart. The general formula for the absolute error is abs(x-y).

**Input:** This routine takes in values x, a machine precision number, and y, an exact value.

**Output:** This routine returns a float representation of the absolute error.

**Usage/Example:**

The routine has two arguments needed to return the value of the absolute error.

      eabs(2.5, 2)

Output from the line above:

      0.5

The returned value of 0.5, is the difference of 2.5 and 2.

**Implementation/Code:** The following is the code for eabs()

      def eabs(x, y):
          return abs(x-y)
