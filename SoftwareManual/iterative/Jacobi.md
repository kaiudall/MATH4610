# Math 4610 Fundamentals of Computational Mathematics

**Routine Name:**           Jacobi

**Author:** Kai Udall

**Language:** Python 3.6.4

**Description/Purpose:** This routine uses Jacobi iteration to solve a system of equations

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

      [0.9999898051082365, 0.9999909097317877, 0.9999895819446051, 0.9999887384560902, 0.9999904956133053]
      
The correct solution is [1,1,1,1,1], as determined by our randomRHS routine
          
**Implementation/Code:** The following is the code for Jacobi
        
        import vectorops as vo
        
        def Jacobi(A, b, x, maxiter=50, tol=10**-17):
            n = len(A)
            itr = 0
            error = tol*10
            while itr < maxiter and error > tol:
                xnew = [0 for k in range(n)]
                for i in range(n):
                    s1 = 0
                    s2 = 0
                    for j in range(i):
                        s1+=A[i][j]*x[j]
                    for j in range(i+1,n):
                        s2+=A[i][j]*x[j]
                    xnew[i] = (b[i] - s1 - s2)/A[i][i]
                error = vo.abserrornorm1(x, xnew)
                itr+=1
                x = xnew
            return x

    
**Last Modified:** November/2018
