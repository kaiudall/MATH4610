# Math 4610 Fundamentals of Computational Mathematics

**Routine Name:**           transpose

**Author:** Kai Udall

**Language:** Python 3.6.4

**Description/Purpose:** This routine returns the transpose of a matrix

**Input:** This routine takes in a matrix

**Output:** This routine returns a matrix

**Usage/Example:**

The routine takes in a matrix

      a = [[1,2,3],[4,5,6],[7,8,9]]
      transpose(a)

Output from the line above:

      [[1, 4, 7], [2, 5, 8], [3, 6, 9]]

The returned value is equal to the transpose of the original matrix

**Implementation/Code:** The following is the code for transpose()

      def transpose(matrix):
          newMatrix = []
          rows = dim(matrix)[0]
          for row in range(rows):
              temprow = []
              for col in matrix:
                  temprow.append(col[row])
              newMatrix.append(temprow)
          return newMatrix


**Last Modified:** October/2018
