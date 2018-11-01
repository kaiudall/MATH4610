# Math 4610 Fundamentals of Computational Mathematics

**Routine Name:**           ge

**Author:** Kai Udall

**Language:** Python 3.6.4

**Description/Purpose:** This routine implements gaussian elimination with no pivoting strategy, for all shapes of matrices

**Input:** This routine takes in a matrix

**Output:** This routine does not return anything, but does reduce the given matrix

**Usage/Example:**

       a = [[1,2,3,4],[1,1,1,1]]
       geSquare(a)
       a
 Output from the line above:
 
       [[1, 0.0, 0.0, 0.0], [1, -1.0, 0.0, 0.0]]
 
 The returned value is the reduced form of the matrix a
 
 **Implementation/Code:** The following is the code for ge()
 
      from copy import copy, deepcopy
      
      def ge(A):
          n, m = vo.dim(A)
          rank = min(n,m)
          highDim = max(n,m)
          # if the matrix is tall
          if n>m:
              a = highDim
              b = rank
          # if the matrix is wide
          elif n<m:
              a = rank
              b = highDim
          # if the matrix is square
          else:
              a = n
              b = n
              # the rank doesn't change, but we can compute
              # one less iteration
              rank-=1
          for k in range(rank):
              for i in range(k+1, a):
                  factor = A[k][i]/A[k][k]
                  for j in range(k, b):
                      A[j][i]-=factor*A[j][k]
      
      
**Last Modified:** October/2018
