# Math 4610 Fundamentals of Computational Mathematics

**Routine Name:**           inducednorminf

**Author:** Kai Udall

**Language:** Python 3.6.4

**Description/Purpose:** This routine computes the induced matrix norm using l_infinity

**Input:** This routine takes in a matrix, and a vector

**Output:** This routine returns the l_infinity norm of the matrix times the vector

**Usage/Example:**

      A = [[1, 2, 3], [4, 5, 6], [9, 8, 9]]
      x = [1,1,1]
      inducednorminf(A, x)

Output from the line above:

      18.0

The returned value is the l_infinity induced matrix norm
          

**Implementation/Code:** The following is the code for inducednorm1
        
        import vectorops as vo
        
        def inducednorminf(A, x):
            Ax = vo.matrixtimesvector(A,x)
            xnorm = vo.norminf(x)
            if xnorm==0:
                return "Failure due to ||x||=0"
            return vo.norminf(Ax)/xnorm

    
**Last Modified:** November/2018
