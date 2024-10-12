# Interview-Questions-of-Python-and-SQL
Interview Questions of Python and SQL
PYTHON INTERVIEW QUESTIONS 
 1.Explain Python's Global Interpreter Lock (GIL). How does it affect multithreading?
   #The GIL is a mutex that protects access to Python objects, preventing multiple native threads from executing Python bytecodes at once. It can limit the performance of CPU-bound programs in multi-core systems because only one thread can execute Python code at a time, though I/O-bound programs benefit from multithreading.
 2.What is the difference between deepcopy() and copy() in Python?
  #Copy() creates a shallow copy of an object, meaning it only copies the outer object, while references to nested objects are preserved. deepcopy() creates a full copy, including nested objects, so changes in the copied object do not affect the original.
 
