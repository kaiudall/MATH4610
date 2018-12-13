# Math 4610 Fundamentals of Computational Mathematics

**Routine Name:**           powerMethod

**Author:** Kai Udall

**Language:** Python 3.6.4

**Description/Purpose:** This routine uses the Power Method to find the largest eigenvalue of a square diagonally dominant matrix

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
      powerMethod(A, x, 10**-10, 10)

Output from the line above:

      [[16, 6, 4, 1, 4], [6, 33, 2, 9, 9], [4, 2, 21, 9, 2], [1, 9, 9, 32, 6], [4, 9, 2, 6, 24]]
      
      50.21302575090172
      

This is the largest eigenvalue
          
**Implementation/Code:** The following is the code for powerMethod():
        
        import vectorops as vo
        def powerMethod(A, v0, tol, maxiter):
            # normalize v0 to a unit vector
            z = vo.vectorscale(v0, 1/vo.norm2(v0))
            error = 10*tol
            # y = Az
            y = vo.matrixtimesvector(A, z)
            # lamb0 = y^T * z
            lamb0 = vo.vectorinnerproduct(y, z)
            k = 0
            while error > tol and k < maxiter:
                # make y a unit vector
                y = vo.vectorscale(y, 1/vo.norm2(y))
                # z = A*y
                z = vo.matrixtimesvector(A, y)
                # lamb1 = y^T*z
                lamb1 = vo.vectorinnerproduct(y, z)
                error = abs(lamb1-lamb0)
                lamb0 = lamb1
                y = z
                k += 1
            return lamb1

    
**Last Modified:** November/2018
