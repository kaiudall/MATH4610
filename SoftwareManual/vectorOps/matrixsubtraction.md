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

**Implementation/Code:** The following is the code for matrixsubtraction()

      def vectorsubtraction(vector1, vector2):
          length = len(vector1)
          return [vector1[i]-vector2[i] for i in range(length)]
    
      def matrixsubtraction(mat1, mat2):
          rows, cols = dim(mat1)
          matrix = []
          for j in range(cols):
              # append the jth col of mat1 from the jth col of mat2
              # using the vector subtraction routine
              matrix.append(vectorsubtraction(mat1[j], mat2[j]))
          return matrix


**Last Modified:** October/2018
