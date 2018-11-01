# Math 4610 Fundamentals of Computational Mathematics

**Routine Name:**           geSquare

**Author:** Kai Udall

**Language:** Python 3.6.4

**Description/Purpose:** This routine implements gaussian elimination with no pivoting strategy, and only for square matrices

**Input:** This routine takes in a matrix

**Output:** This routine returns a the reduced upper triangular matrix

**Usage/Example:**

      a = [[1, 2, 3], [4, 5, 6], [9, 8, 9]]
      geSquare(a)

Output from the line above:

      [[1, 0.0, 0.0], [4, -3.0, 0.0], [9, -10.0, 2.0]]

The returned value is the reduced form of a

**Implementation/Code:** The following is the code for geSquare()

      from copy import copy, deepcopy
      
      def geSquare(A):
          n = len(A)
          # iterate over n-1 pivots
          for k in range(n-1):
              # iterate over elements below the pivot
              for i in range(k+1, n):
                  factor = A[k][i]/A[k][k]
                  # iterate over the columns
                  for j in range(k, n):
                      # Aij=Aij-factor*Akj (k is the pivot row, j is the appropriate column
                      A[j][i]-=factor*A[j][k]
          return A


**Last Modified:** October/2018
