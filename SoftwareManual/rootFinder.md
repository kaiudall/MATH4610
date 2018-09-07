# Math 4610 Fundamentals of Computational Mathematics

**Routine Name:**           rootFinder

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

      [(-0.9999999999999999+1.7320508075688772j), (-1-1.7320508075688772j)]
 
 Where j is python's way of representing i.
      



**Implementation/Code:** The following is the code for rootFinder()

      import numpy as np
      
      def rootFinder(a,b,c):
      # Python takes care of cases where the square root returns a complex number, natively
          positiveRoot = (-b+((b)**2-4*a*c)**0.5)/(2*a)
          negativeRoot = (-b-((b)**2-4*a*c)**0.5)/(2*a)
          return [positiveRoot, negativeRoot]




**Last Modified:** September/2018
