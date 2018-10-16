# Math 4610 Fundamentals of Computational Mathematics

**Routine Name:**           vectorinnerproduct

**Author:** Kai Udall

**Language:** Python 3.6.4

**Description/Purpose:** This routine will compute the inner product of two vectors

**Input:** This routine takes in two vectors

**Output:** This routine returns a scalar

**Usage/Example:**

The routine takes in a vector

      relerrornorm1([1,2,3], [1, 2, 3])

Output from the line above:

      14

The returned value is equal to the inner product of the two vectors

**Implementation/Code:** The following is the code for relerrornorm1()

      def vectorinnerproduct(vector1, vector2):
          length = len(vector1)
          add = 0
          for i in range(length):
              add = add + vector1[i]*vector2[i]
          return add

**Last Modified:** October/2018
