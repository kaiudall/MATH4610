# Math 4610 Fundamentals of Computational Mathematics

**Routine Name:**           norminf

**Author:** Kai Udall

**Language:** Python 3.6.4

**Description/Purpose:** This routine will compute the the l-infinity norm of a vector

**Input:** This routine takes in a vector

**Output:** This routine returns a float

**Usage/Example:**

The routine takes in a vector

      norminf([1,2,3])

Output from the line above:

      3

The returned value is equal to the l-infinity norm of the vector.

**Implementation/Code:** The following is the code for eabs()

      def norm1(vector):
          return max([abs(i) for i in vector])
 
**Last Modified:** October/2018
