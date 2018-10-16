# Math 4610 Fundamentals of Computational Mathematics

**Routine Name:**           vectorcrossproduct

**Author:** Kai Udall

**Language:** Python 3.6.4

**Description/Purpose:** This routine will compute the cross product of two, three dimensional vectors

**Input:** This routine takes in two vectors

**Output:** This routine returns a vector

**Usage/Example:**

The routine takes in 2 vectors

      vectorcrossproduct([1,2,3],[1,2,3])

Output from the line above:

      [0,0,0]

The returned vector is the result of finding the cross product

**Implementation/Code:** The following is the code for vectorcrossproduct

      def vectorcrossproduct(u, v):
          return [u[1]*v[2]-u[2]*v[1], u[2]*v[0]-u[0]*v[2], u[0]*v[1]-u[1]*v[0]]

**Last Modified:** October/2018
