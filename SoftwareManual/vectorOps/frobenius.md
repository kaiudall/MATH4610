# Math 4610 Fundamentals of Computational Mathematics

**Routine Name:**           frobenius

**Author:** Kai Udall

**Language:** Python 3.6.4

**Description/Purpose:** This routine will compute the frobenius norm of a matrix

**Input:** This routine takes in a matrix

**Output:** This routine returns a scalar

**Usage/Example:**

      a = [[1,2,3],[4,5,6],[7,8,9]]
      frobenius(a)

Output from the line above:

      285

The returned value is equal to the frobenius norm of the matrix

**Implementation/Code:** The following is the code for frobenius()

      def frobenius(A):
          colsum = []
          # assuming the matrix is arranged in column vectors
          # iterate over the columns of A
          for col in A:
              temp = []
              # iterate over the ith entry of the row
              for row in col:
                  # append the absolute value of Aij*Aij to temp
                  temp.append(abs(row*row))
              # append the sum of the column to colsum
              colsum.append(sum(temp))
          # returns the sum of all squared entries
          return sum(colsum)



**Last Modified:** October/2018
