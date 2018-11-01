# Math 4610 Fundamentals of Computational Mathematics

**Routine Name:**           vectorscale

**Author:** Kai Udall

**Language:** Python 3.6.4

**Description/Purpose:** This routine will scale a vector

**Input:** This routine takes in a vector, and a scalar

**Output:** This routine returns a vector

**Usage/Example:**

The routine takes in a vector, and scalar

      vectorscale([1,2,3], 2)

Output from the line above:

      [2,4,6]

The returned value is equal to the vector scaled by 2

**Implementation/Code:** The following is the code for vectorscale():

      def vectorscale(vector, scalar):
          return [scalar*i for i in vector]

**Last Modified:** October/2018
