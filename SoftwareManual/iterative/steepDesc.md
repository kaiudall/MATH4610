# Math 4610 Fundamentals of Computational Mathematics

**Routine Name:**           steepDesc

**Author:** Kai Udall

**Language:** Python 3.6.4

**Description/Purpose:** This routine uses Steepest Descent iteration to solve a system of equations

**Input:**

A: User defined symmetric positive definite matrix

b: A vector on the right hand side of the equation

x: An initial guess vector

maxiter: Maximum number of iterations (default 50)

tol: The tolerance for error (default 10**-17)

**Output:** This routine returns an approximate solution vector or the exact solution depending on machine error and iteration specifications

**Usage/Example:**

      A = randomDiagDom(1, 9, 5)
      b = randomRHS(A)
      x = [0.5 for i in range(5)]
      steepDesc(A, b, x)

Output from the line above:

      [0.9999999999999993, 0.9999999999996679, 0.9999999999990693, 1.0000000000005604, 0.9999999999999426]

This is close to the exact solution for our system. (We know this because the randomRHS routine creates b, by multiplying A by a vector of ones).
          
**Implementation/Code:** The following is the code for steepDesc
        
        import vectorops as vo
        
        def steepDesc(A, b, x, maxiter=50, tol=10**-17):
            error = 10*tol
            itr = 0
            while error > tol and itr < maxiter:
                Ax = vo.matrixtimesvector(A, x)
                # r = b - Ax
                r = vo.vectorsubtraction(b, Ax)
                # a = r^T*r / (r^T*A*r)
                a = vo.vectorinnerproduct(r,r)/(vo.vectorinnerproduct(r, vo.matrixtimesvector(A,r)))
                # xnew = x + a*r
                xnew = vo.vectoraddition(x,vo.vectorscale(r, a))
                # 1 norm of r
                error = vo.norm1(r)
                itr+=1
                x = xnew
            return x
    

**Last Modified:** November/2018
