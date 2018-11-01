# Math 4610 Fundamentals of Computational Mathematics

**Routine Name:**           linSolveGE

**Author:** Kai Udall

**Language:** Python 3.6.4

**Description/Purpose:** This routine uses GE and BS to solve a linear system of equations

**Input:** This routine takes in a square matrix, and a vector

**Output:** This routine returns the solution vector

**Usage/Example:**

      A = [[1, 2, 3], [4, 5, 6], [9, 8, 9]]
      b = [1,1,1]
      linSolveGE(A,b)

Output from the line above:

      [-0.33333333333333326, 0.3333333333333333, 0.0]

The returned value is the solution vector x. We can verify this returns a valid solution by calling the matrixtimesvector routine from the vectorops module that was created in chapter 3.

      from vectorops import matrixtimesvector
      
      matrixtimesvector(A, [-0.33333333333333326, 0.3333333333333333, 0.0])
    
Which returns the correct b with some round off error:
      
      [1.0, 1.0, 1.0000000000000002]
          

**Implementation/Code:** The following is the code for fs()

        from copy import copy, deepcopy
        
        def linSolveGE(A,b):
            n = len(A)
            # create copies of A and b, to prevent from altering after GE
            Ab = deepcopy(A)
            bcopy = copy(b)
            # create augmented matrix
            Ab.append(bcopy)
            # eliminate
            ge(Ab)
            # return solution found by backsubstitution
            # Ab[0:len(A)] returns only columns of A
            return bs(Ab[0:n], bcopy)
    
**Last Modified:** November/2018
