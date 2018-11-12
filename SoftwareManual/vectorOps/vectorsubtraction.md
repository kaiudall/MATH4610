# Math 4610 Fundamentals of Computational Mathematics

**Routine Name:**           vectorsubtraction

**Author:** Kai Udall

**Language:** Python 3.6.4

**Description/Purpose:** This routine will subtract two vectors

**Input:** This routine takes in two vectors

**Output:** This routine returns a vector

**Usage/Example:**

The routine takes in a vector

      relerrornorm1([1,2,3], [1, 2, 3])

Output from the line above:

      [0, 0, 0]

The returned value is equal to the two vectors subtracted

**Implementation/Code:** The following is the code for vectorsubtraction()

      def vectorsubtraction(vector1, vector2):
          length = len(vector1)
          # return a vector containing the subtraction of each element
          return [vector1[i]-vector2[i] for i in range(length)]


**Last Modified:** October/2018
