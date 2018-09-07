## Application of Machine Precision in Linear Algebra

After perusing through the internet to find where machine precision is important, I stumbled upon an application in linear algebra. When using Gaussian Elimination, pivoting strategies are actually quite important in order to reduce error. After solving the issue of, "What if we have a pivot that is zero?" it is also important to consider the relative size between pivots. An article titled [Pivoting Techniques in Gaussian Elimination](https://ocw.mit.edu/courses/chemical-engineering/10-34-numerical-methods-applied-to-chemical-engineering-fall-2005/lecture-notes/lecturenotes123.pdf) details out an alteration to Gaussian Elimination called partial pivoting. For each pivoting step, we search for the largest value in the column, and swap the row containing that value to the pivot row. When we apply an elimination step, the pivot then becomes the divisor, so the operations stay smaller rather than grow. This allows computers to maintain more accuracy.