# Math 4610 Fundamentals of Computational Mathematics

**Routine Name:**           abserrornorm2

**Author:** Kai Udall

**Language:** Python 3.6.4

**Description/Purpose:** This routine will compute the the l2 norm of the absolute error between two vectors

**Input:** This routine takes in two vectors

**Output:** This routine returns a float

**Usage/Example:**

The routine takes in a vector

      abserrornorm2([1,2,3], [1, 2.1, 2.99])

Output from the line above:

      0.10049875621120898

The returned value is equal to the l1 norm of the absolute error between the two vectors.

**Implementation/Code:** The following is the code for abserrornorm2()

      def abserrornorm2(vector1, vector2):
          length = len(vector1)
          add = 0
          for i in range(length):
              err = error.eabs(vector1[i], vector2[i])
              add = add + err*err
          return add**0.5




 
**Last Modified:** October/2018
