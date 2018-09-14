# Math 4610 Fundamentals of Computational Mathematics

**Routine Name:**           Graph Error

**Author:** Kai Udall

**Language:** Python 3.6.4

**Description/Purpose:** This routine uses the derivApprox routine, an error routine, and matplotlib to graph the approximate error of the derivative approximation as h tends towards zero.

**Input:** This routine takes in several arguments. 

errortype, either error.eabs or error.erel, which correspond to absolute error or relative error. 

rangelist, a list of powers that h is taken to the power of (negative values recommended). 

trueValue, the actual value of the derivative of the function at x. 

function, the function that the routine will use for the derivative approximation.

x, where the derivative will be evaluated at.

h, the base used as the h trends towards zero.

**Output:** This routine returns a list of values for the derivative approximation as the value of h changes, that can then be plotted.

**Usage/Example:**

The routine is called by errorlist with argument descriptions found in the Input section of this page.

      errorlist(error.eabs, range(0, -55, -1), 2, f, 1, 2)

Output from the line above:

      [1.0, 0.5, 0.25, 0.125, 0.0625, 0.03125, 0.015625, 0.0078125, 0.00390625, 0.001953125, 0.0009765625, 0.00048828125, 0.000244140625, 0.0001220703125, 6.103515625e-05, 3.0517578125e-05, 1.52587890625e-05, 7.62939453125e-06, 3.814697265625e-06, 1.9073486328125e-06, 9.5367431640625e-07, 4.76837158203125e-07, 2.384185791015625e-07, 1.1920928955078125e-07, 5.960464477539063e-08, 2.9802322387695312e-08, 1.4901161193847656e-08, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 2.0, 2.0]
      
This call of the routine returns a list that improves until h=2**-53. At which point the machine calling this routine stores h as 0, and so the approximate derivative becomes ((2+0)^2-2^2)/2=0, and the absolute error becomes abs(0-2)=2.
      



**Implementation/Code:** The following is the code for errorlist():

      import sys
      sys.path.append('shared/library/directory')
      import derivapprox as dap
      import error
      
      def errorlist(errortype, rangelist, trueValue, function, x, h):
          for i in rangelist:
              ddxapprox = dap.derivApprox(function, x, h**i)
              if ddxapprox = dap.derivApprox(function, x, h**i)
              # The following if statement checks for a case where using the relative error
              # will result in a division by error issue, and then suggests a new range to avoid
              # further errors with graphing
              if ddxapprox==0.0 and errortype==error.erel:
                  print("h**i reached 0, which will cause a division by zero error")
                  print("Change range max to:")
                  print(i)
                  return elist
              else:
                  elist.append(errortype(ddxapprox, trueValue)
          return elist
          
The following is the code for graphing an errorlist:

      errorAbsf1x2h = errorlist(error.eabs, range(0, -55, -1), 2 f, 1, 2)
      plt.plot(range(0, -55, -1), errorRelf1x2h)
      plt.xlabel('log2(h)')
      plt.ylabel('Error')
      plt.title('Absolute Error Derivative x^2 using h=2')
      plt.show()

[Absolute Error for the derivative approximation of x^2 using h=2 as a base]()




**Last Modified:** September/2018
