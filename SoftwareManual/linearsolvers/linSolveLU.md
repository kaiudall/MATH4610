# Math 4610 Fundamentals of Computational Mathematics

**Routine Name:**           linSolveLU

**Author:** Kai Udall

**Language:** Python 3.6.4

**Description/Purpose:** This routine uses LU, FS, and BS to solve a linear system of equations

**Input:** This routine takes in a square matrix, and a vector

**Output:** This routine returns the solution vector

**Usage/Example:**

      A = [[1, 2, 3], [4, 5, 6], [9, 8, 9]]
      b = [1,1,1]
      linSolveLU(A,b)

Output from the line above:

      [-0.33333333333333326, 0.3333333333333333, 0.0]

The returned value is the solution vector x. We can verify this returns a valid solution by calling the matrixtimesvector routine from the vectorops module that was created in chapter 3.

      from vectorops import matrixtimesvector
      
      matrixtimesvector(A, [-0.33333333333333326, 0.3333333333333333, 0.0])
    
Which returns the correct b with some round off error:
      
      [1.0, 1.0, 1.0000000000000002]
          

**Implementation/Code:** The following is the code for linSolveLU()
        
        def linSolveLU(A,b):
            # LU decomp
            # don't worry about altering A, the LU routine does not alter it
            L, U = LU(A)
            # forward solve for y
            y = fs(L, b)
            # backward solve for x
            return bs(U, y)

    
**Last Modified:** November/2018
