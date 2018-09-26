# Math 4610 Fundamentals of Computational Mathematics

**Routine Name:**           bisnewton

**Author:** Kai Udall

**Language:** Python 3.6.4

**Description/Purpose:** This routine will find the approximation for a root of a given function using a bombination of the bisection routine and the newton routine.

**Input:** The routine takes in arguments:

function: The function we want to find the root for

derivative: The derivative for the function

x1: The starting left bound for bisection

x2: The starting right bound for bisection

tolerance: The user specified tolerance for error

maxiter: The maximum iterations the routine will go through before halting

**Output:** This routine returns the approximate route for the function(hopefully).

**Usage/Example:**

The user can call the function in the following manner:
      
      def f(x):
          return x**2 - 3
      
      def df(x):
          return 2*x
          
      bisnewton(f, df, 0, 10, 10**-5, 2)

Output from the line above:

      1.7320508075688774

The returned value is the approximate root.

As per the homework we will also find a root of sin(pi*x). 

      import sin from math
      import pi from math
      
      bisnewton(lambda x: sin(pi*x), lambda x: pi*cos(pi*x), .5, 1.9, 10**-16, 3)

Output from the line above
      1.0

**Implementation/Code:** The following is the code for secant.
      
      def bisnewton(function, derivative, x1, x2, tolerance, maxiter):
          mid = 0.5*(x1+x2)
          error = 1
          itr = 0
          while error >= tolerance and itr < maxiter:
              x, converge = newton(function, derivative, mid, 10*tolerance, 15)
              # When the algorithm converges quickly the indexing will throw an error
              # These branching statements insure the convergence error is long enough
              # to check for the error
              if len(converge) > 2:
                  error = abs(converge[-1]-converge[-2])
              else:
                  error = 1
              mid = bisection(function, x1, x2, 10**-1, 4)
              itr += 1
          return x


      


**Last Modified:** September/2018
