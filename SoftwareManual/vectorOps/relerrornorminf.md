# Math 4610 Fundamentals of Computational Mathematics

**Routine Name:**           relerrornorminf

**Author:** Kai Udall

**Language:** Python 3.6.4

**Description/Purpose:** This routine will compute the the l-inf norm of the relative error between two vectors

**Input:** This routine takes in two vectors, the first being the true vector, the second a vector with some error

**Output:** This routine returns a float

**Usage/Example:**

The routine takes in a vector

      relerrornorminf([1,2,3], [1, 2.1, 2.99])

Output from the line above:

      0.050000000000000044

The returned value is equal to the l-inf norm of the relative error between the two vectors.

**Implementation/Code:** The following is the code for relerrornorminf()

      # From the error chapter of this manual, we import the relative error routine
      from error import erel
      
      def relerrornorminf(vector1, vector2):
          length = len(vector1)
          # compute the relative error of each entry
          errors = [erel(vector1[i], vector2[i] for i in range(length)]
          # return the maximum relative error
          return max(errors)


**Last Modified:** October/2018
