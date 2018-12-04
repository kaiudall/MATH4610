# Math 4610 Fundamentals of Computational Mathematics

**Routine Name:**           cholesky

**Author:** Kai Udall

**Language:** Python 3.6.4

**Description/Purpose:** This routine implements Cholesky factorization on symmetric possitive definite matrices

**Input:** This routine takes in a square matrix, that is comprised of a list of lists, with each component list being a column vector

**Output:** This routine returns the upper triangular matrix of the Cholesky

**Usage/Example:**

       import iterative as it
       
       # Create a symmetric positive definite matrix
       A = it.randomDiagDom(1,9,10)
       A
       
       cholesky(A)
       
 Output from the line above:
 
       [[30, 7, 6, 8, 2], [7, 23, 4, 2, 3], [6, 4, 27, 6, 3], [8, 2, 6, 26, 8], [2, 3, 3, 8, 24]]
       
       [[5.477225575051661, 0, 0, 0, 0], [1.2780193008453875, 4.622409184253019, 0, 0, 0], [1.0954451150103321, 0.5624772486298527, 5.048130282072145, 0, 0], [1.4605934866804429, 0.028844987109223258, 0.8683958428296742, 4.807465371018441, 0], [0.3651483716701107, 0.548054755075241, 0.45397633207003246, 1.467847676521854, 4.604957257190963]]
 
 The first output is the matrix A, the second is the upper triangular matrix created by using the cholesky factorization
 
 **Implementation/Code:** The following is the code for cholesky()
 
      def cholesky(A):
          n = len(A)
          # create an empty matrix
          R = vo.zeros(n, n)
          for i in range(n):
              for k in range(i+1):
                  tmp_sum = sum(R[i][j] * R[k][j] for j in range(k))
                  if i==k:
                      R[i][k] = sqrt(A[i][i] - tmp_sum)
                  else:
                      R[i][k] = (1/R[k][k] *(A[i][k] - tmp_sum))
          return R
      
      
**Last Modified:** November/2018
