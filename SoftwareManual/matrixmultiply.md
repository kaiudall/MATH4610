# Math 4610 Fundamentals of Computational Mathematics

**Routine Name:**           matrixmultiply
**Author:** Kai Udall

**Language:** Python 3.6.4

**Description/Purpose:** This routine computes the inner product of a matrix 1 (m by n) and matrix 2 (n by q), and returns a new matrix (m by q)

**Input:** This routine takes in two matrices of compatible dimensions

**Output:** This routine returns a matrix

**Usage/Example:**
The two vectors are defined below, where a is 2 by 3 and b is the transpose of a, 3 by 2.
      a = [[1, 2], [3, 4], [5, 6]]
      b = transpose(a)
      matrixmultiply(a,b)

Output from the line above:

      [[35, 44], [44, 56]]

The returned value is equal to the inner product of the two matrices, a 2 by 2 matrix

**Implementation/Code:** The following is the code for matrixmultiply()

      def matrixmultiply(matrix1, matrix2):
          # to easily access the rows of matrix1, we will just transpose it
          # so we can iterate over the rows instead of cols
          matrix1T = transpose(matrix1)
          newMatrix = []
          for row in matrix1T:
              temprow = []
              for col in matrix2:
                  temprow.append(vectorinnerproduct(row, col))
              newMatrix.append(temprow)
          # we appended the rows to the new matrix, to get the matrix
          # in standard form [[col1], [col2],...,[coln]], we need
          # to take the transpose again
          return transpose(newMatrix)


**Last Modified:** October/2018
