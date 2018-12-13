# Math 4610 Fundamentals of Computational Mathematics

**Routine Name:**           condition

**Author:** Kai Udall

**Language:** Python 3.6.4

**Description/Purpose:** This routine uses Inverse Iteration and the power method to find the 2 condition number

**Input:**

A: User defined symmetric positive definite matrix

v0: An initial guess vector

tol: The tolerance for error

maxiter: Maximum number of iterations

**Output:** This routine returns an approximate 2-condition number depending on machine error and iteration specifications

**Usage/Example:**

      import iterative as it
      
      A = it.randomDiagDom(1, 9, 5)
      A
      # a zero vector of length 5
      x = [0.5 for i in range(5)]
      condtion(A, x, 10**-10, 10)

Output from the line above:

      [[16, 6, 4, 1, 4], [6, 33, 2, 9, 9], [4, 2, 21, 9, 2], [1, 9, 9, 32, 6], [4, 9, 2, 6, 24]]
      
      425.4422052011697
      

This is the condition
          
**Implementation/Code:** The following is the code for condition():
        
        def condition(A, v0, tol, maxiter):
            lambdaMax = powerMethod(A, v0power, tol, maxiter)
            lambdaMin = inverseIteration(A, v0inverse, tol, maxiter)
            return lambdaMax*lambdaMin

    
**Last Modified:** November/2018
