# Math 4610 Fundamentals of Computational Mathematics

**Routine Name:**           matrixaddition

**Author:** Kai Udall

**Language:** Python 3.6.4

**Description/Purpose:** This routine will add two matrices

**Input:** This routine takes in two matrices

**Output:** This routine returns a matrix

**Usage/Example:**

The routine takes in 2 matrices

      a = [[1,2,3],[4,5,6],[7,8,9]]
      matrixaddition(a,a)

Output from the line above:

      [[2, 4, 6], [8, 10, 12], [14, 16, 18]]

The returned value is equal to the two matrices added together

**Implementation/Code:** The following is the code for matrixaddition()

      def matrixaddition(mat1, mat2):
          rows, cols = dim(mat1)
          matrix = []
          for j in range(cols):
              # add col j of mat1 to col j of mat 2, append that vector to matrix
              matrix.append(vectoraddition(mat1[j], mat2[j]))
          return matrix


**Last Modified:** October/2018
