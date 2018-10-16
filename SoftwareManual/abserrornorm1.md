# Math 4610 Fundamentals of Computational Mathematics

**Routine Name:**           abserrornorm1

**Author:** Kai Udall

**Language:** Python 3.6.4

**Description/Purpose:** This routine will compute the the l1 norm of the absolute error between two vectors

**Input:** This routine takes in two vectors

**Output:** This routine returns a float

**Usage/Example:**

The routine takes in a vector

      abserrornorm1([1,2,3], [1, 2.1, 2.99])

Output from the line above:

      0.10999999999999988

The returned value is equal to the l1 norm of the absolute error between the two vectors.

**Implementation/Code:** The following is the code for abserrornorm1()

      def abserrornorm1(vector1, vector2):
          length = len(vector1)
          add = 0
          for i in range(length):
              add = add + error.eabs(vector1[i], vector2[i])
          return add


 
**Last Modified:** October/2018
