# Math 4610 Fundamentals of Computational Mathematics

**Routine Name:**           matrixtimesvector

**Author:** Kai Udall

**Language:** Python 3.6.4

**Description/Purpose:** This routine computes the inner product of a matrix (m by n) and a vector (n by 1), and returns a vector (m by 1)

**Input:** This routine takes in a matrix, and an a vector

**Output:** This routine returns a vector

**Usage/Example:**

      a = [[1, 2], [3, 4], [5, 6]]
      b = [1, 2, 3]
      matrixtimesvector(a,b)

Output from the line above:

      [22, 28]

The returned value is equal to the product of matrix a and vector b

**Implementation/Code:** The following is the code for matrixtimesvector()

      def matrixtimesvector(matrix, vector):
          # taking the transpose of the matrix allows the rows to more easily be accessed by iteration
          matrixT = transpose(matrix)
          newVector = []
          for row in matrixT:
              newVector.append(vectorinnerproduct(row, vector))
          return newVector


**Last Modified:** October/2018
