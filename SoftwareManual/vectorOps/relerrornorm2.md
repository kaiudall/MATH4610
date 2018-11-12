# Math 4610 Fundamentals of Computational Mathematics

**Routine Name:**           relerrornorm2

**Author:** Kai Udall

**Language:** Python 3.6.4

**Description/Purpose:** This routine will compute the the l2 norm of the relative error between two vectors

**Input:** This routine takes in two vectors, the first being the true vector, the second a vector with some error

**Output:** This routine returns a float

**Usage/Example:**

The routine takes in a vector

      relerrornorm1([1,2,3], [1, 2.1, 2.99])

Output from the line above:

      0.05011098792790973

The returned value is equal to the l2 norm of the relative error between the two vectors.

**Implementation/Code:** The following is the code for relerrornorm2()

      # From the error chapter of this manual, we import the relative error routine
      from error import erel
      
      def relerrornorm2(vector1, vector2):
          length = len(vector1)
          add = 0
          for i in range(length):
              err = erel(vector1[i], vector2[i])
              add = add + err*err
          return add**0.5


**Last Modified:** October/2018
