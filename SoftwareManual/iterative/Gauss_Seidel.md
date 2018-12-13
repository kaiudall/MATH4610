# Math 4610 Fundamentals of Computational Mathematics

**Routine Name:**           Gauss_Seidel

**Author:** Kai Udall

**Language:** Python 3.6.4

**Description/Purpose:** This routine uses Gauss Seidel iteration to solve a system of equations

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
      Jacobi(A, b, x)

Output from the line above:

      [1.0, 1.0, 1.0, 1.0, 1.0]

This is the exact solution for our system. (We know this because the randomRHS routine creates b, by multiplying A by a vector of ones).
          
**Implementation/Code:** The following is the code for Gauss_Seidel
        
        import vectorops as vo
        
        def Gauss_Seidel(A, b, x, maxiter=50, tol=10**-17):
            n = len(A)
            itr = 0
            error = tol*10
            while itr < maxiter and error > tol:
                xnew = [0 for k in range(n)]
                for i in range(n):
                    s1 = 0
                    s2 = 0
                    # dot product of A and xnew up to element i
                    for j in range(i):
                        s1+=A[i][j]*xnew[j]
                    # dot product of A and x of i+i to n
                    for j in range(i+1,n):
                        s2+=A[i][j]*x[j]
                    xnew[i] = (b[i]- s1 - s2)/A[i][i]
                # 1-norm of x-xnew
                error = vo.abserrornorm1(x, xnew)
                itr+=1
                x = xnew
            return x

    
**Last Modified:** November/2018
