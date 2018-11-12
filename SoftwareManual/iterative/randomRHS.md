# Math 4610 Fundamentals of Computational Mathematics

**Routine Name:**           randomRHS

**Author:** Kai Udall

**Language:** Python 3.6.4

**Description/Purpose:** This routine uses a diagonally dominant matrix as an imput, and multiplies it by a vector containing ones, of the appropriate size

**Input:**

A: Diagonally dominant matrix

**Output:** This routine returns a vector

**Usage/Example:**

      A = randomDiagDom(-9, 9, 5)
      randomRHS(A)

Output from the line above:

      [-4, 22, 18, 14, 1]
          
**Implementation/Code:** The following is the code for randomRHS
        
        import vectorops as vo
        
        def randomRHS(A):
            # create a vector of ones corresponding to the size of A
            onevec = [1 for i in range(len(A))]
            return vo.matrixtimesvector(A, onevec)

    
**Last Modified:** November/2018
