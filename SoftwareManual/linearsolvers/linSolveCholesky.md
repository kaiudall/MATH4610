# Math 4610 Fundamentals of Computational Mathematics

**Routine Name:**           linSolveCholesky

**Author:** Kai Udall

**Language:** Python 3.6.4

**Description/Purpose:** This routine uses cholesky, and the forward and backward substitution routines

**Input:** This routine takes in a matrix that has already been factored with cholesky

**Output:** This routine returns the solution vector

**Usage/Example:**

      import iterative as it
      # create a 5 by 5 symmetric positive definite matrix
      A = it.randomDiagDom(1,9,5)
      A
      
      b = it.randomRHS(A)
      b
      
      U = cholesky(A)
      linSolveCholesky(U, b)

Output from the line above:

      [[21, 2, 1, 8, 1], [2, 18, 1, 8, 1], [1, 1, 13, 5, 5], [8, 8, 5, 30, 6], [1, 1, 5, 6, 17]]
      
      [33, 26.857142857142858, 22.06417112299465, 26.245494095711624, 14.45678028220634]
      
      [1.0000000000000002, 0.9999999999999998, 1.0, 1.0, 0.9999999999999999]
      
The first line is the matrix A. The second line is the vector b (which is set to be a vector of ones times A). The third line is the solution vector x.
          

**Implementation/Code:** The following is the code for linSolveCholesky()
        
        def linSolveCholesky(U, b):
            # the lower triangular matrix is equal to the transpose
            L = vo.transpose(U)
            # solve Ly=b with forward substitution
            y = fs(L, b)
            # solve Ux=y with backward substitution
            return bs(U, y)

    
**Last Modified:** December/2018
