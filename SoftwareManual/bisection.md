# Math 4610 Fundamentals of Computational Mathematics

**Routine Name:**           bisection

**Author:** Kai Udall

**Language:** Python 3.6.4

**Description/Purpose:** This routine will find the approximation for a root of a given function using the bisection algorithm.

**Input:** The routine takes in arguments:

function: The function we want to find the root for

x1: The starting left bound for the algorithm

x2: The starting right bound for the algorithm

tolerance: The user specified tolerance for error

maxiter: The maximum iterations the routine will go through before halting

**Output:** This routine returns a 2 item tuple which contains the value of the last iteration, and a list of the approximations of the root as it (hopefully) converges.

**Usage/Example:**

The user can call the function in the following manner:

      bisection(lambda x: x**2 - 3, -2, 0, 10**-16, 15)

Output from the line above:

      (-1.73199462890625, [-1.0, -1.5, -1.75, -1.625, -1.6875, -1.71875, -1.734375, -1.7265625, -1.73046875, -1.732421875, -1.7314453125, -1.73193359375, -1.732177734375, -1.7320556640625, -1.73199462890625])

The first value (-1.73199462890625) is the approximation for a root of x^2 - 3. The second item is a list of the values returned as the routine converged.

As per the homework we will also find a root of cos(pi*x). 

      fpi(lambda x: (x+2/pi^2)/(x+1), 0.4, 10**-5, 15)

returns (0.4501548887710996, [0.45009818433425897, 0.4501354174983731, 0.45014953562692434, 0.4501548887710996])
Which is impressive because I used only a first order taylor series approximation, and the true root is at 0.5.

**Implementation/Code:** The following is the code for fpi()

      import sin
      
      def fpi(function, x0, tolerance, maxiter):
          error = 1
          itr = 0
          converge = []
          while error > tolerance and itr < maxiter:
              x = function(x0)
              error = abs(x0-x)
               x0 = x
              converge.append(x0)
              itr += 1
          return (x, converge)


**Last Modified:** September/2018
