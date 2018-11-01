# Math 4610 Fundamentals of Computational Mathematics

**Routine Name:**           relerrornorm1

**Author:** Kai Udall

**Language:** Python 3.6.4

**Description/Purpose:** This routine will compute the the l1 norm of the relative error between two vectors

**Input:** This routine takes in two vectors, the first being the true vector, the second a vector with some error

**Output:** This routine returns a float

**Usage/Example:**

The routine takes in a vector

      relerrornorm1([1,2,3], [1, 2.1, 2.99])

Output from the line above:

      0.05333333333333331

The returned value is equal to the l1 norm of the relative error between the two vectors.

**Implementation/Code:** The following is the code for relerrornorm1()

      def relerrornorm1(vector1, vector2):
          length = len(vector1)
          add = 0
          for i in range(length):
              add = add + error.erel(vector1[i], vector2[i])
          return add



**Last Modified:** October/2018
