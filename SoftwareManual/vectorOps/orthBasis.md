# Math 4610 Fundamentals of Computational Mathematics

**Routine Name:**           orthBasis

**Author:** Kai Udall

**Language:** Python 3.6.4

**Description/Purpose:** This routine takes in two, two dimensional independent vectors and returns two unit vectors of the same dimension that form an orthogonal basis.

**Input:** This routine takes in two, 2-D vectors

**Output:** This routine returns two, 2-D orthogonal unit vectors in a tuple

**Usage/Example:**

The two vectors are defined below

      u = [2,1]
      v = [1,3]
      c = orthBasis(u, v)
      c
      vectorinnerproduct(u, v)
      norm2(c[0])
      norm2(c[1])

Output from the lines above:

      ([0.8944271909999157, 0.44721359549995787], [-0.8944271909999157, 0.44721359549995787])
      
      0
      
      1
      
      1

The first line being the two vectors in a tuple, the second being the evaluation of the dot product to insure that the vectors are orthogonal, the last two lines confirm the output vectors are unit in length.

**Implementation/Code:** The following is the code for orthBasis()

      from copy import copy
      
      def orthBasis(u, v):
          # compute the projection of v onto u
          projuv = vectorscale(u, vectorinnerproduct(u, v)/norm2(u)**2)
          # turn the projection vector into a unit vector
          projuv = vectorscale(projuv, 1/norm2(projuv))
          # copy the projection
          orth = copy(projuv)
          # we can easily create an orthogonal vector by changing the sign of the first component
          orth[0] = orth[0]*-1
          # return the projection and its orthogonal vector in a tuple
          return (projuv, orth)


**Last Modified:** October/2018
