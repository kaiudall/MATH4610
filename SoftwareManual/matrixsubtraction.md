# Math 4610 Fundamentals of Computational Mathematics

**Routine Name:**           matrixsubtraction

**Author:** Kai Udall

**Language:** Python 3.6.4

**Description/Purpose:** This routine will subtract two matrices

**Input:** This routine takes in two matrices

**Output:** This routine returns a matrix

**Usage/Example:**

The routine takes in 2 matrices

      a = [[1,2,3],[4,5,6],[7,8,9]]
      matrixsubtraction(a,a)

Output from the line above:

      [[0,0,0], [0,0,0], [0,0,0]]

The returned value is equal to matrix1-matrix2

**Implementation/Code:** The following is the code for matrixaddition()

      def matrixsubtraction(mat1, mat2):
          rows = dim(mat1)[0]
          cols = dim(mat2)[1]
          matrix = []
          for i in range(cols):
              matrix.append(vectorsubtraction(mat1[i], mat2[i]))
          return matrix


**Last Modified:** October/2018
