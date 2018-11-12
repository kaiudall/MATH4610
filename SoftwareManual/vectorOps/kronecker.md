# Math 4610 Fundamentals of Computational Mathematics

**Routine Name:**           kronecker

**Author:** Kai Udall

**Language:** Python 3.6.4

**Description/Purpose:** This routine computes the kronecker product of matrix 1 (m by n) and matrix 2 (p by q), and returns a new matrix (mp by nq)

**Input:** This routine takes in two matrices

**Output:** This routine returns a matrix

**Usage/Example:**

The two vectors are defined below, where a is 2 by 3 and b is the transpose of a, 3 by 2.

      a = [[1,1,1],[1,1,1],[1,1,1]]
      b = [[1,2,3],[4,5,6],[7,8,9]]
      c = kronecker(a,b)
      c
      transpose(c)

Output from the line above:

      [[1, 2, 3, 1, 2, 3, 1, 2, 3], [4, 5, 6, 4, 5, 6, 4, 5, 6], [7, 8, 9, 7, 8, 9, 7, 8, 9], [1, 2, 3, 1, 2, 3, 1, 2, 3], [4, 5, 6, 4, 5, 6, 4, 5, 6], [7, 8, 9, 7, 8, 9, 7, 8, 9], [1, 2, 3, 1, 2, 3, 1, 2, 3], [4, 5, 6, 4, 5, 6, 4, 5, 6], [7, 8, 9, 7, 8, 9, 7, 8, 9]]
      
      [[1, 4, 7, 1, 4, 7, 1, 4, 7], 
       [2, 5, 8, 2, 5, 8, 2, 5, 8], 
       [3, 6, 9, 3, 6, 9, 3, 6, 9], 
       [1, 4, 7, 1, 4, 7, 1, 4, 7], 
       [2, 5, 8, 2, 5, 8, 2, 5, 8], 
       [3, 6, 9, 3, 6, 9, 3, 6, 9], 
       [1, 4, 7, 1, 4, 7, 1, 4, 7], 
       [2, 5, 8, 2, 5, 8, 2, 5, 8], 
       [3, 6, 9, 3, 6, 9, 3, 6, 9]]

The first line being the kronecker product printed in columns, the secon output being the transpose so that I could easily show it's matrix form

**Implementation/Code:** The following is the code for matrixmultiply()

      def kronecker(A,B):
          m, n = dim(A)
          p, q = dim(B)
          AoxB = []
          # A, i index m rows, j index n cols
          # B, k index p rows, l index q cols
          for j in range(n):
              for l in range(q):
                  tempcol = []
                  for i in range(m):
                      for k in range(p):
                          tempcol.append(A[j][i]*B[l][k])
                  AoxB.append(tempcol)
          return AoxB


**Last Modified:** October/2018
