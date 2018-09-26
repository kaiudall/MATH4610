# Math 4610 Fundamentals of Computational Mathematics

**Routine Name:**           bissecant

**Author:** Kai Udall

**Language:** Python 3.6.4

**Description/Purpose:** This routine will find the approximation for a root of a given function using a bombination of the bisection routine and the secant routine.

**Input:** The routine takes in arguments:

function: The function we want to find the root for

x1: The starting left bound for bisection

x2: The starting right bound for bisection

tolerance: The user specified tolerance for error

maxiter: The maximum iterations the routine will go through before halting

**Output:** This routine returns the approximate route for the function(hopefully).

**Usage/Example:**

The user can call the function in the following manner:
      
      def f(x):
          return x**2 - 3
          
      bissecant(f, 0, 10, 10**-16, 3)

Output from the line above:

      1.7320508075688772

The returned value is the approximate root.

As per the homework we will also find a root of sin(pi*x). 

      import sin from math
      import pi from math
      
      bissecant(lambda x: sin(pi*x), 0.1,1.9, 10**-15,3)

Output from the line above
      1.0

**Implementation/Code:** The following is the code for bissecant.
      
      def bissecant(function, x1, x2, tolerance, maxiter):
          error = 1
          itr = 0
          while error > tolerance and itr < maxiter:
              x, converge = secant(function, x1, x2, tolerance, 15)
              x1 = min(converge[-1], converge[-2])
              x2 = max(converge[-1], converge[-2])
              error = abs(x1-x2)
              x, converge = bisection(function, x1, x2, 10**-1, 4)
              itr += 1
          return x




      


**Last Modified:** September/2018
