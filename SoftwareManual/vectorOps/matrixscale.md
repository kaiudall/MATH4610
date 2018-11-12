# Math 4610 Fundamentals of Computational Mathematics

**Routine Name:**           matrixscale

**Author:** Kai Udall

**Language:** Python 3.6.4

**Description/Purpose:** This routine returns a matrix scaled by a number

**Input:** This routine takes in a matrix, and an a scalar

**Output:** This routine returns a matrix

**Usage/Example:**

The routine takes in a matrix

      a = [[1,2,3],[4,5,6],[7,8,9]]
      matrixscale(a, 2)

Output from the line above:

      [[2, 4, 6], [8, 10, 12], [14, 16, 18]]

The returned value is equal to the transpose of the original matrix

**Implementation/Code:** The following is the code for matrixscale()

      def matrixscale(matrix, scalar):
          rows, cols = dim(matrix)
          for col in range(cols):
              for row in range(rows):
                  matrix[col][row]*=scalar
          return matrix


**Last Modified:** October/2018
