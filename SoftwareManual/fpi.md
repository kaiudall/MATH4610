# Math 4610 Fundamentals of Computational Mathematics

**Routine Name:**           fpi

**Author:** Kai Udall

**Language:** Python 3.6.4

**Description/Purpose:** This routine finds the root of a given function using the fixed point iteration process. The fixed point algorithm can be described as:

Given a scalar continuous function in one variable, f(x), select a function g(x) such that x satisfies f(x)=0 if and only if g(x)=x. Then:

1. Start from an initial guess x0.

2. For k=0,1,2,..., set x_(k+1)=g(x_k) until x_(k+1) satisfies termination criteria.

**Input:** This routine takes a function, an inital point, x0, and two iteration conditions. maxiter, the maximum amount of iterations before the routine stops, and tolerance, the amount of error there is allowed to be.

**Output:** This routine (might) return a root for the given function

**Usage/Example:**

The routine is called by fpi.

      def f(x):
          return (x+3)/(x+1)
          
      fpi(f, 1.2, 10**-100, 100)

Output from the line above:

      (1.7320508075688772, [1.909090909090909, 1.6875, 1.744186046511628, 1.7288135593220337, 1.7329192546583851, 1.731818181818182, 1.7321131447587357, 1.7320341047503045, 1.7320552831029872, 1.7320496083550914, 1.7320511288973837, 1.7320507214691736, 1.7320508306392242, 1.7320508013871965, 1.7320508092252536, 1.7320508071250524, 1.7320508076877998, 1.7320508075370122, 1.7320508075774155, 1.7320508075665895, 1.7320508075694903, 1.7320508075687129, 1.7320508075689216, 1.7320508075688652, 1.7320508075688805, 1.7320508075688765, 1.7320508075688774, 1.7320508075688772, 1.7320508075688772])
      
This call of the routine returns a tuple with two items. The first item in the tuple is 1.7320508075688772, the second item in the tuple is a list of the iterations through the routine.
      



**Implementation/Code:** The following is the code for errorlist():

      def fpi(function, x0, tolerance, maxiter):
          error = 1
          itr = 0
          xiter = []
              while(error > tolerance and itr < maxiter):
              x = function(x0)
              error = abs(x0-x)
              x0 = x
              xiter.append(x0)
              itr += 1
          return (x, xiter)
