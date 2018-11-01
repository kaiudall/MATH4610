# Math 4610 Fundamentals of Computational Mathematics

**Routine Name:**           bs

**Author:** Kai Udall

**Language:** Python 3.6.4

**Description/Purpose:** This routine implements forward substitution on a square upper triangular matrix

**Input:** This routine takes in an upper triangular matrix and a vector

**Output:** This routine returns the solution vector

**Usage/Example:**

      A = [[1, 0.0, 0.0], [4, -3.0, 0.0], [9, -10.0, 2.0]]
      b = [1,2,3]
      bs(A,b)

Output from the line above:

      [10.166666666666668, -5.666666666666667, 1.5]

The returned value is the solution vector x. We can verify this returns a valid solution by calling the matrixtimesvector routine from the vectorops module that was created in chapter 3.

      from vectorops import matrixtimesvector
      
      matrixtimesvector(A, [10.166666666666668, -5.666666666666667, 1.5])
    
Which returns the correct b:
      
      [1.0, 2.0, 3.0]
          

**Implementation/Code:** The following is the code for bs()

        def bs(U,b):
            n = len(U)
            # creating an appropriately sized x vector is less efficient
            # but easier to index over
            x = [0 for i in range(n)]
            # the nth element in python is index n-1
            x[n-1]=b[n-1]/U[n-1][n-1]
            # iterate over the rows from the n-1 row to the first row
            for i in range(n-2, -1, -1):
                # iterate over the columns from the ith column to the nth column
                for j in range(i, n):
                    b[i]-=U[j][i]*x[j]
                x[i]=b[i]/U[i][i]
            return x   
      
**Last Modified:** November/2018
