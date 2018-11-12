# Math 4610 Fundamentals of Computational Mathematics

**Routine Name:**           inducednorm1

**Author:** Kai Udall

**Language:** Python 3.6.4

**Description/Purpose:** This routine computes the induced norm of a matrix and vector

**Input:** This routine takes in a matrix, and a vector

**Output:** This routine returns the l1 norm of the matrix times the vector

**Usage/Example:**

      A = [[1, 2, 3], [4, 5, 6], [9, 8, 9]]
      x = [1,1,1]
      inducednorm1(A, x)

Output from the line above:

      15.666666666666666

The returned value is the l1 induced matrix norm
          

**Implementation/Code:** The following is the code for inducednorm1
        
        import vectorops as vo
        
        def inducednorm1(A, x):
            Ax = vo.matrixtimesvector(A,x)
            xnorm = vo.norm1(x)
            if xnorm==0:
                return "Failure due to ||x||=0"
            return vo.norm1(Ax)/xnorm

    
**Last Modified:** November/2018
