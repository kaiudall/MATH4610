# Math 4610 Fundamentals of Computational Mathematics Software Manual 

**Routine Name:**           smaceps

**Author:** Kai Udall

**Language:** Python 3.6.4

**Description/Purpose:** This routine will compute the single precision value for the machine epsilon or the number of digits
in the representation of real numbers in single precision. This is a routine for analyzing the behavior of any computer. This
usually will need to be run one time for each computer.

**Input:** There are no inputs needed in this case.

**Output:** This routine returns a single precision value for the number of decimal digits that can be represented on the
computer being queried.

**Usage/Example:**

The routine has two arguments needed to return the values of the precision in terms of the smallest number that can be
represented. Python does not support single point precision natively. By using the numpy package numbers can be forced to be
represented in single point precision.

      smaceps()

Output from the line above:

      (24, 5.9604645e-08)

The first value (24) is the number of binary digits that define the machine epsilon and the second is related to the
decimal version of the same value. The number of decimal digits that can be represented is roughly eight (E-08 on the
end of the second value).

**Implementation/Code:** The following is the code for smaceps()

      import numpy as np
      
      def smaceps():
          # Define seps, one, appone
          one = np.float32(1.0)
          seps = np.float32(1.0)
          appone = one + seps

          # loop, dividing by 2 each time to determine when the difference
          # between one and the approximation is zero in single precision

          ipow = 0
          for i in range(1,10001):
                  ipow = ipow + 1

                  # update the perturbation and compute the approximation to one

                  seps = np.float32(seps / 2)
                  appone = one + seps

                  # do the comparison and if small enough, break out of the loop
                  # and return control to the calling code

                  if abs(appone-one)==0:
                      return (ipow,seps)

                  # if the code gets to this point, there is a bit of trouble

                  elif i==1000:
                      print('The loop limit has been exceeded')


**Last Modified:** September/2018
