# Matrix Multiply Parallel

Here is my code that pulls in the dotProduct that is ran parallel.

      # Cython code
      def matrixMultiply(double[:,:] A, double[:,:] B):
          cdef int rowsA = A.shape[0]
          cdef int colsA = A.shape[1]
          cdef int rowsB = B.shape[0]
          cdef int colsB = B.shape[1]
          cdef double[:,:] C = np.zeros((rowsA, colsB))
          cdef int i, j
          for i in range(rowsA):
              for j in range(colsB):
                  C[i,j] = dotProduct(A[i], B[:,j])
          return np.asarray(C)
      
      # ran in python
      # 640 by 640 matrix of ones
      import parallelvectorops as pvo
      
      A = np.array([[1.0 for i in range(640)] for i in range(640)])
      pvo.matrixMultiply(A,A)
      
Returns
      
      array([[640., 640., 640., ..., 640., 640., 640.],
             [640., 640., 640., ..., 640., 640., 640.],
             [640., 640., 640., ..., 640., 640., 640.],
              ...,
             [640., 640., 640., ..., 640., 640., 640.],
             [640., 640., 640., ..., 640., 640., 640.],
             [640., 640., 640., ..., 640., 640., 640.]])
