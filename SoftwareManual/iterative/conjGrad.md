# Math 4610 Fundamentals of Computational Mathematics

**Routine Name:**           conjGrad

**Author:** Kai Udall

**Language:** Python 3.6.4

**Description/Purpose:** This routine uses the conjugate gradient method to solve a system of equations

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

      # Math 4610 Fundamentals of Computational Mathematics

**Usage/Example:**

      A = randomDiagDom(1, 9, 5)
      b = randomRHS(A)
      x = [0.5 for i in range(5)]
      steepDesc(A, b, x)

Output from the line above:

      [0.9818927759360633, 0.8968528743002875, 0.8212618506240421, 0.9913416538955939, 1.1425237012480842]

This is a poor solution to our system. I'm going to look into how I implemented the routine to make sure that I 
          
**Implementation/Code:** The following is the code for conjGrad

        import vectorops as vo
        
        def conjGrad(A, b, x, maxiter=50, tol=10**-17):
            Ax = vo.matrixtimesvector(A, x)
            # r = b - Ax
            r = vo.vectorsubtraction(b, Ax)
            # delta = r^T*r
            delta = vo.vectorinnerproduct(r,r)
            # bdelta = b^T*b
            bdelta = vo.vectorinnerproduct(b,b)
            itr = 0
            p = r
            while delta > tol*tol*bdelta and itr < maxiter:
                # s = Ap
                s = vo.matrixtimesvector(A, p)
                # a = delta/(p^T * s)
                a = delta/vo.vectorinnerproduct(p, s)
                # xnew = x + a*p
                xnew = vo.vectoraddition(x, vo.vectorscale(p, a))
                # rnew = r + a*p
                rnew = vo.vectorsubtraction(r, vo.vectorscale(s, a))
                # deltanew = rnew^T * r
                deltanew = vo.vectorinnerproduct(rnew, r)
                # pnew = rnew + (deltanew/delta)*p
                pnew = vo.vectoraddition(rnew, vo.vectorscale(p, (deltanew/delta)))
                x = xnew
                r = rnew
                delta = deltanew
                p = pnew
                itr+=1
    return x

**Last Modified:** November/2018
