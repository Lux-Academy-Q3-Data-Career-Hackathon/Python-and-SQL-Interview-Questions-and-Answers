PYTHON INTERVIEW QUESTIONS

---

1. Explain Python's Global Interpreter Lock (GIL). How does it affect multithreading?
+ The GIL is a mutex that protects access to Python objects, preventing multiple native threads from executing Python bytecodes at once. It can limit the performance of CPU-bound programs in multi-core systems because only one thread can execute Python code at a time, though I/O-bound programs benefit from multithreading.
2. What is the difference between deepcopy() and copy() in Python?
+ Copy() creates a shallow copy of an object, meaning it only copies the outer object, while references to nested objects are preserved.
+ Deepcopy() creates a full copy, including nested objects, so changes in the copied object do not affect the original.
3. How does Python's memory management work? Explain garbage collection in Python.
+ Python uses reference counting and a cyclic garbage collector to manage memory. Reference counting is the primary method; when an object’s reference count drops to zero, it's immediately deallocated.
+ The cyclic garbage collector identifies and cleans up cyclic references that are not freed by reference counting.
4. How would you implement a singleton pattern in Python?
+ You can implement a singleton pattern using various approaches in Python, such as by overriding the __new__ method, using a class-level variable, or employing a decorator or metaclass to ensure only one instance of the class is created.
5. What are Python generators? How do they differ from regular functions?
+ Generators are functions that yield values one at a time, allowing iteration over potentially large datasets without storing the entire dataset in memory. They differ from regular functions by using yield instead of return, and they return an iterator.

---