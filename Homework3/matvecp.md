# Matrix Vector Parallel

This page demonstrates that I implemented a parallel version of matrix times vector.

The following is the code for my matrix vector multiplication written in cython. The file has to be saved as a .pyx file. In my case I called it parallelvectorops.pyx

      cimport openmp
      import numpy as np
      from cython.parallel cimport prange
      from cython.parallel cimport parallel
      
      #create a function only callable in cython
      cdef dotProduct(double[:] u, double[:] v):
          cdef double add = 0
          cdef int n = u.shape[0]
          cdef int i
          # prange is a python function that runs a for loop in parallel using OPENMP
          for i in prange(n, nogil=True):
              add += u[i]*v[i]
          return add
      
      #callable in python
      def matrixTimesVector(double[:,:] A, double [:] b, int rows):
          # create an empty vector that stores the values from the iterated dot product
          cdef double[:] newVector = np.empty(rows, 'd')
          cdef int i
          for i in range(rows):
              newVector[i] = dotProduct(A[i], b)
          # this allows the returned object to be viewable in python
          return np.asarray(newVector)
    
Here is a set up file so that we can compile the .pyx into c and .so. This file should be in the same directory and be called setup.py
      
      from distutils.core import setup
      from Cython.Build import cythonize
      from distutils.extension import Extension
      from Cython.Distutils import build_ext
      
      setup(
        name = "parallelvectorops",
        cmdclass = {"build_ext": build_ext},
        ext_modules =
        [
          Extension("parallelvectorops",
                    ["parallelvectorops.pyx"],
                    extra_compile_args = ["-O0", "-fopenmp"],
                    extra_link_args=['-fopenmp']
                    )
        ]
      )
      
Start a terminal session in the same directory as the file

      python setup.py build_ext --inplace

The resulting files will be created (except for try.py that is the file I used to call matrix times vector in python)

![demonstrated](https://github.com/kaiudall/MATH4610/blob/master/Homework3/Screen%20Shot%202018-12-10%20at%205.28.37%20PM.png)

In try.py I call the function from cython

      import numpy as np
      import parallelvectorops as pvo
      
      # numpy plays nice with openmp
      A = np.column_stack([[i*1.0 for i in range(3)] for i in range(4)])
      A
      b = np.array([1.0, 2.0, 3.0, 4.0])
      b
      
      pvo.matrixTimesVector(A,b)
      
The following is the results:

      # A
      array([[0., 0., 0., 0.],
             [1., 1., 1., 1.],
             [2., 2., 2., 2.]])
      
      # b
      array([1., 2., 3., 4.])
      
      # A times b
      array([ 0., 10., 20.])
