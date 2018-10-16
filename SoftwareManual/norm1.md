# Math 4610 Fundamentals of Computational Mathematics

**Routine Name:**           norm1

**Author:** Kai Udall

**Language:** Python 3.6.4

**Description/Purpose:** This routine will compute the the l1 norm of a vector

**Input:** This routine takes in a vector

**Output:** This routine returns a float

**Usage/Example:**

The routine takes in a vector

      norm1([1,2,3])

Output from the line above:

      6

The returned value is equal to the l1 norm of the vector.

**Implementation/Code:** The following is the code for norm1()

      def norm1(vector):
          add = 0
          for i in vector:
              add = add + i
          return add
 
**Last Modified:** October/2018
