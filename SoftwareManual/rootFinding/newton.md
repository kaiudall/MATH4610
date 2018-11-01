# Math 4610 Fundamentals of Computational Mathematics

**Routine Name:**           newton

**Author:** Kai Udall

**Language:** Python 3.6.4

**Description/Purpose:** This routine will find the approximation for a root of a given function using the newton algorithm.

**Input:** The routine takes in arguments:

function: The function we want to find the root for

derivative: The derivative of the function

x0: The starting point for the algorithm to be evaluated at

tolerance: The user specified tolerance for error

maxiter: The maximum iterations the routine will go through before halting

**Output:** This routine returns a 2 item tuple which contains the value of the last iteration, and a list of the approximations of the root as it (hopefully) converges.

**Usage/Example:**

The user can call the function in the following manner:
      def f(x):
          return x**2 - 3
          
      def df(x):
          return 2x
      
      newton(f, df, 1.5, 10**-8, 15)

Output from the line above:

      (1.7320508075688772, [1.75, 1.7321428571428572, 1.7320508100147276, 1.7320508075688772])

The first value (1.7320508075688772) is the approximation for a root of x^2 - 3. The second item is a list of the values returned as the routine converged.

As per the homework we will also find a root of sin(pi*x). 

      import sin from math
      import cos from math
      import pi from math
      
      def g(x):
          return sin(pi*x)
      
      def dg(x):
          return pi*cos(pi*x)
      
      newton(g, dg, 0.9, 10**-16, 15)

Output from the line above
      (1.0, [1.0034251515267683, 0.999999867798016, 1.0, 1.0])

**Implementation/Code:** The following is the code for newton.
      
      def newton(function, derivative, x0, tolerance, maxiter):
          newt = lambda x: x-function(x)/derivative(x)
          error = 1
          itr = 0
          converge = []
          while error > tolerance and itr < maxiter:
              x = newt(x0)
              error = abs(x0-x)
              x0 = x
              converge.append(x0)
              itr += 1
          return (x, converge)
      


**Last Modified:** September/2018
