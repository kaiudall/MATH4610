# Math 4610 Fundamentals of Computational Mathematics

**Routine Name:**           Relative Error

**Author:** Kai Udall

**Language:** Python 3.6.4

**Description/Purpose:** This routine will compute the relative error of a given value, and its computational counterpart. The general formula for the relative error is abs(x-y)/x.

**Input:** This routine takes in values x, a machine precision number, and y, an exact value.

**Output:** This routine returns a float representation of the relative error.

**Usage/Example:**

The routine has two arguments needed to return the value of the relative error.

      erel(2.5, 2)

Output from the line above:

      0.2

The returned value of 0.2, which is the relative error.

**Implementation/Code:** The following is the code for erel()

      def erel(x, y):
          return abs(x-y)/x
