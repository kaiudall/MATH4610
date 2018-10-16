# Math 4610 Fundamentals of Computational Mathematics

**Routine Name:**           norm2

**Author:** Kai Udall

**Language:** Python 3.6.4

**Description/Purpose:** This routine will compute the the l2 norm of a vector

**Input:** This routine takes in a vector

**Output:** This routine returns a float

**Usage/Example:**

The routine takes in a vector

      norm2([1,2,3])

Output from the line above:

      3.7416573867739413

The returned value is equal to the l2 norm of the vector.

**Implementation/Code:** The following is the code for norm2()

      def norm1(vector):
          add = 0
          for i in vector:
              add = add + i**2
          return add**0.5
 
**Last Modified:** October/2018
