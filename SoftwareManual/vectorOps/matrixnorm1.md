# Math 4610 Fundamentals of Computational Mathematics

**Routine Name:**           matrixnorm1

**Author:** Kai Udall

**Language:** Python 3.6.4

**Description/Purpose:** This routine will compute the l1 norm of a matrix

**Input:** This routine takes in a matrix that is a list of column vectors

**Output:** This routine returns a scalar

**Usage/Example:**

      a = [[1,2,3],[4,5,6],[7,8,9]]
      matrixnorm1(a)

Output from the line above:

      24

The returned value is equal to the l1 norm of the matrix

**Implementation/Code:** The following is the code for frobenius()

      def matrixnorm1(A):
          # this routine rerturns the maximum absolute solumn sum
          colsums = []
          # iterate over the columns of A
          # assuming the matrix is arranged in column vectors
          for col in A:
              abscolsum = []
              # iterate over the ith row of col
              for row in col:
                  # append the absolute value of Aij to abscolsum
                  abscolsum.append(abs(row))
              # append the absolute colum sum to colsums
              colsums.append(sum(abscolsum))
          # return the max abs col sum
          return max(colsums)


**Last Modified:** October/2018
