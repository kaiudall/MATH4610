# Math 4610 Fundamentals of Computational Mathematics

**Routine Name:**           secant

**Author:** Kai Udall

**Language:** Python 3.6.4

**Description/Purpose:** This routine will find the approximation for a root of a given function using the secant algorithm.

**Input:** The routine takes in arguments:

function: The function we want to find the root for

x0: The first value for x of the secant line

x1: The second value for x of the secant line

tolerance: The user specified tolerance for error

maxiter: The maximum iterations the routine will go through before halting

**Output:** This routine returns a 2 item tuple which contains the value of the last iteration, and a list of the approximations of the root as it (hopefully) converges.

**Usage/Example:**

The user can call the function in the following manner:
      secant(lambda x: x**2-3, -2, -1.9, 10**-16, 15)

Output from the line above:

      (-1.7320508075688772, [-1.7435897435897434, -1.7325826882477129, -1.732052573113379, -1.7320508078399186,   -1.7320508075688774, -1.7320508075688772, -1.7320508075688772])

The first value (-1.7320508075688772) is the approximation for a root of x^2 - 3. The second item is a list of the values returned as the routine converged.

As per the homework we will also find a root of sin(pi*x). 

      import sin from math
      import pi from math
      
      secant(lambda x: sin(pi*x), .8, 0.9, 10**-16, 15)

Output from the line above
      (1.0, [1.0108508539255465, 0.9998392948089997, 1.0000000306678771, 0.9999999999999988, 1.0, 1.0])

**Implementation/Code:** The following is the code for secant.
      
      def secant(function, x0, x1, tolerance, maxiter):
          error = 1
          itr = 0
          converge = []
          while error > tolerance and itr < maxiter:
              x2 = x1 - (function(x1)*(x1-x0))/(function(x1)-function(x0))
              converge.append(x2)
              error = abs(x2-x1)
              x0 = x1
              x1 = x2
              itr += 1
          return (x2, converge)
      


**Last Modified:** September/2018
