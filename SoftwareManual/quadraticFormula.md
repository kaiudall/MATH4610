# Math 4610 Fundamentals of Computational Mathematics

**Routine Name:**           quadraticFormula

**Author:** Kai Udall

**Language:** Python 3.6.4

**Description/Purpose:** This routine finds the roots of a given 2nd degree polynomial.

**Input:** The routine takes the coefficients from the desired polynomial ax^2+bx+c.

**Output:** This routine returns a list of the roots found.

**Usage/Example:**

The routine is called by rootFinder() with a, b, and c corresponding to the polynomial's corresponding coefficients.

      rootFinder(1,4,4):

Output from the line above:

      [2.0, 2.0]
      
The routine also can handle cases where the roots are complex.

      rootFinder(1,2,4)

Gives the output:

      [(-1+1.7320508075688772j), (-1-1.7320508075688772j)]
 
 Where j is python's way of representing i.
      



**Implementation/Code:** The following is the code for rootFinder()

      from math import sqrt
      
      def quadraticFormula(a,b,c):
          innards = b**2-4*a*c
          # if the expression inside the square root is negative
          # python's square root function will throw a runtime error
          if innards<0:
              # to avoid a runtime error we make the expression positive
              innards*=-1
              # take the square root of the positive expression, make it
              # a string, concatenate the python equivalent to i, which is j,
              # to our root, then coerce the string to a complex
              root = complex(str(sqrt(innards))+'j')
              positiveRoot = (-b + root)/2*a
              negativeRoot = (-b - root)/2*a
              return [positiveRoot, negativeRoot]
          else:
              positiveRoot = (-b + sqrt(innards))/(2*a)
              negativeRoot = (-b - sqrt(innards))/(2*a)
    return [positiveRoot, negativeRoot]
      

**Last Modified:** September/2018
