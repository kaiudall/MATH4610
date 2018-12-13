# Math 4610 Fundamentals of Computational Mathematics

**Routine Name:**           inverseIteration

**Author:** Kai Udall

**Language:** Python 3.6.4

**Description/Purpose:** This routine uses Inverse Iteration to find the smallest eigenvalue of a square diagonally dominant matrix

**Input:**

A: User defined symmetric positive definite matrix

v0: An initial guess vector

tol: The tolerance for error

maxiter: Maximum number of iterations

**Output:** This routine returns an approximate eigenvalue depending on machine error and iteration specifications

**Usage/Example:**

      import iterative as it
      
      A = it.randomDiagDom(1, 9, 5)
      A
      # a zero vector of length 5
      x = [0.5 for i in range(5)]
      inverseIteration(A, x, 10**-10, 10)

Output from the line above:

      [[16, 6, 4, 1, 4], [6, 33, 2, 9, 9], [4, 2, 21, 9, 2], [1, 9, 9, 32, 6], [4, 9, 2, 6, 24]]
      
      8.472745843114815
      

This is the smalest eigenvalue
          
**Implementation/Code:** The following is the code for powerMethod():
        
        import vectorops as vo
        import linearSolvers as ls
        
        def inverseIteration(A, v0, tol, maxiter):
            # make z a unit vector
            z = vo.vectorscale(v0, 1/vo.norm2(v0))
            # LU decomp
            L, U = ls.LU(A)
            # solve for y
            y = ls.linSolveLU(L, U, z)
            # mew0 = z^T*y
            mew0 = vo.vectorinnerproduct(z, y)
            error = 10*tol
            k = 0
            while error > tol and k < maxiter:
                # make y a unit vector
                y = vo.vectorscale(y, 1/vo.norm2(y))
                # solve for z
                z = ls.linSolveLU(L, U, y)
                # z^T*y
                mew1 = vo.vectorinnerproduct(z, y)
                error = abs(mew1 - mew0)
                mew0 = mew1
                y = z
                k += 1
            return 1/mew1

    
**Last Modified:** November/2018
