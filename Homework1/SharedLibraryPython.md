## Implementation of a "shared library" in Python

This is how to import python modules from any directory on my computer, instead of just in the same directory as the given .py file.

# 1.

Set up the directory with the py files that you want to be shared. Create a blank file titled __init__.py in the directory.

# 2.

From a different location, create a new py file.

At the top of the file type:
      
      import sys
      sys.path.append('/path/to/the/folder/above/your/package/directory/')
      from package import module
      
      # You can now call functions in that module by
      module.function()
