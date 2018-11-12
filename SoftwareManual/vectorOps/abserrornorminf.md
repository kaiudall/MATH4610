# Math 4610 Fundamentals of Computational Mathematics

**Routine Name:**           abserrornorminf

**Author:** Kai Udall

**Language:** Python 3.6.4

**Description/Purpose:** This routine will compute the the l-infinity norm of the absolute error between two vectors

**Input:** This routine takes in two vectors

**Output:** This routine returns a float

**Usage/Example:**

The routine takes in a vector

      abserrornorminf([1,2,3], [1, 2.1, 2.99])

Output from the line above:

      0.10000000000000009

The returned value is equal to the l-infinity norm of the absolute error between the two vectors.

**Implementation/Code:** The following is the code for abserrornorminf()

      def abserrornorminf(vector1, vector2):
          length = len(vector1)
          return max([abs(vector1[i]-vector2[i]) for i in range(length)])



**Last Modified:** October/2018
