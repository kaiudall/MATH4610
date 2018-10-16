# Math 4610 Fundamentals of Computational Mathematics

**Routine Name:**           vectoraddition

**Author:** Kai Udall

**Language:** Python 3.6.4

**Description/Purpose:** This routine will add two vectors

**Input:** This routine takes in two vectors

**Output:** This routine returns a vector

**Usage/Example:**

The routine takes in a vector

      relerrornorm1([1,2,3], [1, 2, 3])

Output from the line above:

      [2, 4, 6]

The returned value is equal to the two vectors added together

**Implementation/Code:** The following is the code for vectoraddition()

      def vectoraddition(vector1, vector2):
          length = len(vector1)
          return [vector1[i]+vector2[i] for i in range(length)]


**Last Modified:** October/2018
