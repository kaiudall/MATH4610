# Math 4610 Fundamentals of Computational Mathematics

**Routine Name:**           determinant
**Author:** Kai Udall

**Language:** Python 3.6.4

**Description/Purpose:** This routine computes the determinant of a square matrix, using gaussian elimination (with no pivoting strategy), and using the property that the product of the diagonals in a triangular matrix is the determinant.

**Input:** This routine takes in one matrix

**Output:** This routine returns a float

**Usage/Example:**

      a = [[1, 2, 3], [4, 5, 6], [7, 8, 9]]
      determinant(a)

Output from the line above:

      0

The returned value is equal to the determinant of matrix a.

**Implementation/Code:** The following is the code for matrixmultiply()

      from copy import copy
      def determinant(matrix):
          # copying the original matrix to preserve it
          Matrix = copy(matrix)
          n = len(Matrix)
          for k in range(n-1):
              for i in range(k+1,n):
                  factor = Matrix[k][i]/Matrix[k][k]
                  for j in range(k, n):
                      Matrix[j][i]-=factor*Matrix[j][k]
          det = 1
          for p in range(n):
              det *= Matrix[p][p]
          return det


**Last Modified:** October/2018
