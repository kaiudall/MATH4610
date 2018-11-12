# Math 4610 Fundamentals of Computational Mathematics

**Routine Name:**           randomDiagDom

**Author:** Kai Udall

**Language:** Python 3.6.4

**Description/Purpose:** This routine creates a square matrix of a user designated size that is diagonally dominant and has Aij=Aji, with random integers as elements

**Input:**

a: the lower range of random integers

b: the upper range of upper integers

n: size of the square matrix

**Output:** This routine returns a diagonally dominant square matrix

**Usage/Example:**

      A = randomDiagDom(-9,9,5)
      A

Output from the line above:

      [[10, 6, 4, 1, 4], [6, 23, -6, 2, -8], [4, -6, 18, 2, 3], [1, 2, 2, 4, -6], [4, -8, 3, -6, 28]]

The returned value fits the specifications outlined in the description. To check that Aij=Aji we can import the transpose routine from the vectorops routine in this manual.

      import vectorops as vo
      
      vo.transpose(A)
      
Which returns:

      [[10, 6, 4, 1, 4], [6, 23, -6, 2, -8], [4, -6, 18, 2, 3], [1, 2, 2, 4, -6], [4, -8, 3, -6, 28]]
      
Which is equal to the matrix we made before
          

**Implementation/Code:** The following is the code for randomDiagDom
        
        import vectorops as vo
        
        def randomDiagDom(a, b, n):
            # make an empty square n by n matrix
            mat = vo.zeros(n,n)
            for i in range(n):
                for j in range(i+1,n):
                    num = randint(a,b)
                    # make the upper triangle and lower triangle equal
                    mat[j][i] = num
                    mat[i][j] = num
                # add the sum of the absolute values of all elements in each row to a random integer
                # and set the integer as the value for the diagonal. This insures the matrix is diagonally
                # dominant and still pseudo-random
                mat[i][i] = sum([abs(mat[k][i]) for k in range(n)]) + randint(a,b)
            return mat

    
**Last Modified:** November/2018
