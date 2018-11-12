# Math 4610 Fundamentals of Computational Mathematics

**Routine Name:**           matrixnorminf

**Author:** Kai Udall

**Language:** Python 3.6.4

**Description/Purpose:** This routine will compute the l-inf norm of a matrix

**Input:** This routine takes in a matrix that is a list of column vectors

**Output:** This routine returns a scalar

**Usage/Example:**

      a = [[1,2,3],[4,5,6],[7,8,9]]
      matrixnorminf(a)

Output from the line above:

      18

The returned value is equal to the l-inf norm of the matrix

**Implementation/Code:** The following is the code for matrixnorminf()

      def matrixnorminf(A):
          # this routine returns the maximum absolute row sum
          # m is number rows, n is number of cols
          m, n = dim(A)
          rowsums = []
          # iterate over rows
          for i in range(m):
              temprow = []
              # iterate over cols
              for j in range(n):
                  # append the abs value of the jth column of row i to temprow
                  temprow.append(abs(A[j][i]))
              # append the sum of temprow
              rowsums.append(sum(temprow))
          # return the max row sum
          return max(rowsums)


**Last Modified:** October/2018
