# Math 4610 Fundamentals of Computational Mathematics

**Routine Name:**           LU

**Author:** Kai Udall

**Language:** Python 3.6.4

**Description/Purpose:** This routine implements LU decomposition, using GE as a base, with no pivoting strategy

**Input:** This routine takes in a square matrix

**Output:** This routine returns L and U in a tuple

**Usage/Example:**

       A = [[1,2,3],[4,5,6],[7,8,9]]
       LU(A)
       
 Output from the line above:
 
       ([[1, 2.0, 3.0], [0, 1, 2.0], [0, 0, 1]], [[1, 0.0, 0.0], [4, -3.0, 0.0], [9, -10.0, 2.0]])
 
 The returned value is a tuple that has the matrix L, as the first item, and U as the second item
 
 **Implementation/Code:** The following is the code for ge()
 
      def LU(A):
          n = len(A)
          # create an identity matrix of size n by n
          L = identity(n)
          # create a copy of A
          U = deepcopy(A)
          # typical GE, but save the factors to L
          for k in range(n-1):
              for i in range(k+1,n):
                  # saving the factor temporarily and in L, allows the routine
                  # to use factor, without having to worry about indexing in
                  # the next loop
                  factor = U[k][i]/U[k][k]
                  L[k][i] = factor
                  for j in range(k,n):
                      U[j][i]-=factor*U[j][k]
          return (L,U)
      
      
**Last Modified:** November/2018
