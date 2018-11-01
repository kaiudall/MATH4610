# Math 4610 Fundamentals of Computational Mathematics

**Routine Name:**           fs
**Author:** Kai Udall

**Language:** Python 3.6.4

**Description/Purpose:** This routine implements forward substitution on a square lower triangular matrix

**Input:** This routine takes in an lower traingular matrix and a vector

**Output:** This routine returns the solution vector

**Usage/Example:**

      A = [[1, 4, 9], [0.0, -3.0, -10.0], [0.0, 0.0, 2.0]]
      b = [1,2,3]
      fs(A,b)

Output from the line above:

      [1.0, 0.6666666666666666, 0.33333333333333304]

The returned value is the solution vector x. We can verify this returns a valid solution by calling the matrixtimesvector routine from the vectorops module that was created in chapter 3.

      from vectorops import matrixtimesvector
      
      matrixtimesvector(A, [1.0, 0.6666666666666666, 0.33333333333333304])
    
Which returns the correct b:
      
      [1.0, 2.0, 3.0]
          

**Implementation/Code:** The following is the code for fs()

        def fs(L, b):
          n = len(L)
          x = []
          # computing the first x outside the loop allows
          # for this indexing scheme
          x.append(b[0]/L[0][0])
          # iterate from the second row to the last row
          for i in range(1,n):
              # iterate over the columns up to the ith column
              for j in range(i):
                  b[i]-=L[j][i]*x[j]
              x.append(b[i]/L[i][i])
          return x    
      
**Last Modified:** November/2018
