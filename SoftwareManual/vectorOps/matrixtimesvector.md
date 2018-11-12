# Math 4610 Fundamentals of Computational Mathematics

**Routine Name:**           matrixtimesvector

**Author:** Kai Udall

**Language:** Python 3.6.4

**Description/Purpose:** This routine computes the inner product of a matrix (m by n) and a vector (n by 1), and returns a vector (m by 1)

**Input:** This routine takes in a matrix arranged as a list of column vectors, and a vector

**Output:** This routine returns a vector

**Usage/Example:**

      a = [[1, 2], [3, 4], [5, 6]]
      b = [1, 2, 3]
      matrixtimesvector(a,b)

Output from the line above:

      [22, 28]

The returned value is equal to the product of matrix a and vector b

**Implementation/Code:** The following is the code for matrixtimesvector()

      def dim(matrix):
          cols = len(matrix)
          rows = len(cols)
          return (rows, cols)

      def vectorinnerproduct(vector1, vector2):
          length = len(vector1)
          add = 0
          for i in range(length):
              add = add + vector1[i]*vector2[i]
          return add
      
      def matrixtimesvector(matrix, vector):
          # assuming matrix is a list of column vectors
          rows, cols = dim(matrix)
          b = []
          for i in range(rows):
              temprow = []
              for j in range(cols):
                  temprow.append(matrix[j][i])
              b.append(vectorinnerproduct(temprow, vector))
          return b


**Last Modified:** October/2018
