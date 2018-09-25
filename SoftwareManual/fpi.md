# Math 4610 Fundamentals of Computational Mathematics

**Routine Name:**           fpi

**Author:** Kai Udall

**Language:** Python 3.6.4

**Description/Purpose:** This routine will find the approximation for a root of a given function using the fixed point iteration algorithm.

**Input:** The routine takes in arguments:

function: A function g(x) that is a representation of the function that we want to find the root of

x0: Where the fixed point algorithm will be evaluated at to start

tolerance: The user specified tolerance for error

maxiter: The maximum iterations the routine will go through before halting

**Output:** This routine returns a 2 item tuple which contains the value of the last iteration, and a list of the approximations of the root as it (hopefully) converges.

**Usage/Example:**

The user first needs to define the function that is wanted for the fixed point algorithm, and then we can input all of the arguments the routine requires. In this case we want to find a root for x^2 - 3. We will use (x+3)/(x+1) for our function for the routine.

      def g(x):
          return (x+3)/(x+1)
      
      fpi(g, -3.2, 10**-10, 15)

Output from the line above:

      (1.7320507769002793, [0.09090909090909098, 2.833333333333333, 1.5217391304347827, 1.7931034482758623, 1.7160493827160495, 1.736363636363636, 1.7308970099667773, 1.732360097323601, 1.7319679430097954, 1.7320730117340286, 1.7320448580291101, 1.732052401746725, 1.7320503804104597, 1.7320509220256481, 1.7320507769002793])

The first value (1.7320507769002793) is the approximation for a root of x^2 - 3. The second item is a list of the values returned as the routine converged.

As per the homework we will also find a root of cos(pi*x). 
I decided to use a taylor series approximation (1 - pi^2 * x^2/2)and then rewrite the function to a form similar to what we used for x^2 - 3. Doing this we get g(x) = (x+2/pi^2)/(x+1).

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

