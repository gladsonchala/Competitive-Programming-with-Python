# Python speed and performance trick

1. **Choose the Right Data Structure**:
   - Use appropriate data structures like lists, sets, dictionaries, etc., depending on your use case.
   - Example:
     ```python
     # Using a dictionary for fast lookup
     phonebook = {'Alice': '123-456', 'Bob': '789-012', 'Charlie': '345-678'}
     ```

2. **Sorting**:
   - Utilize efficient sorting methods like the built-in `sort()` function with the `key` parameter or list comprehensions.
   - Example:
     ```python
     # Sorting a list of tuples based on the second element
     data = [(3, 'c'), (1, 'a'), (2, 'b')]
     sorted_data = sorted(data, key=lambda x: x[1])
     ```

3. **String Concatenation**:
   - Avoid repeated string concatenation in loops, as it creates new strings each time.
   - Use `join()` for efficient string concatenation.
   - Example:
     ```python
     # Inefficient string concatenation
     result = ''
     for word in words:
         result += word

     # Efficient string concatenation using join()
     result = ''.join(words)
     ```

4. **Loops**:
   - Use list comprehensions or generator expressions for compact and efficient loops.
   - Example:
     ```python
     # Using list comprehension
     squares = [x ** 2 for x in range(10)]

     # Using generator expression
     squares_gen = (x ** 2 for x in range(10))
     ```

5. **Avoiding Dots**:
   - Reduce function call overhead by caching function references.
   - Example:
     ```python
     # Caching function references
     my_func = some_module.some_function
     result = my_func(data)
     ```

6. **Local Variables**:
   - Use local variables instead of global variables for improved performance.
   - Example:
     ```python
     def my_function():
         local_var = 42
         # Use local_var instead of accessing a global variable
     ```

7. **Initializing Dictionary Elements**:
   - Optimize dictionary initialization and element updates using techniques like `try-except` or the `get()` method.
   - Example:
     ```python
     # Using try-except
     my_dict = {}
     for word in words:
         try:
             my_dict[word] += 1
         except KeyError:
             my_dict[word] = 1
     ```

8. **Import Statement Overhead**:
   - Minimize import statement overhead by placing imports strategically.
   - Example:
     ```python
     def my_function():
         import math  # Import inside function
         return math.sqrt(2)
     ```

9. **Data Aggregation**:
   - Aggregate data and perform operations in bulk to reduce function call overhead.
   - Example:
     ```python
     # Aggregating data and performing operations
     def process_data(data):
         total = sum(data)
         average = total / len(data)
         return total, average
     ```

10. **Using xrange instead of range**:
    - Use `xrange` instead of `range` for large ranges to save memory.
    - Example:
      ```python
      # Using xrange for large ranges
      for i in xrange(1000000):
          # Do something
      ```

11. **Re-map Functions at runtime**:
    - Dynamically re-map functions at runtime to avoid unnecessary condition checks.
    - Example:
      ```python
      class Test:
          def __init__(self):
              self.func = self.check_first

          def check_first(self, data):
              # Check condition first
              pass

          def check_second(self, data):
              # Check condition later
              pass
      ```

12. **Profiling Code**:
    - Use profiling tools like `profile`, `cProfile`, or `trace` to identify performance bottlenecks.
    - Example:
      ```python
      import cProfile

      def my_function():
          # Function code

      cProfile.run('my_function()')
      ```

13. **Using Built-in Functions**:
    - Leverage built-in functions for common operations instead of reinventing the wheel.
    - Example:
      ```python
      # Using built-in functions
      data = [1, 2, 3, 4, 5]
      max_value = max(data)
      ```

14. **Memory Management**:
    - Manage memory efficiently by deallocating resources when they're no longer needed, especially in resource-intensive applications.
    - Example:
      ```python
      # Efficient memory management
      with open('large_file.txt', 'r') as file:
          data = file.read()
          # Process data
      ```

15. **Optimizing Function Calls**:
    - Minimize function calls inside loops by moving them outside whenever possible.
    - Example:
      ```python
      # Optimizing function calls
      def process_data(data):
          # Process data here
          pass

      # Move function call outside the loop
      processed_data = []
      for item in my_data:
          processed_data.append(process_data(item))
      ```

16. **Lazy Evaluation**:
    - Utilize lazy evaluation techniques to defer computation until it's actually needed.
    - Example:
      ```python
      # Lazy evaluation
      def lazy_operation():
          # Compute result only when needed
          pass

      result = lazy_operation()  # Result computed here
      ```

17. **Using Cython**:
    - Use Cython to compile Python code to C for improved performance, especially in CPU-bound applications.
    - Example:
      ```python
      # Using Cython for performance optimization
      # my_module.pyx
      def my_function():
          # Cython code here
          pass
      ```

18. **NumPy and Pandas**:
    - Utilize NumPy and Pandas for numerical and data manipulation tasks respectively, as they're optimized for performance.
    - Example:
      ```python
      # Using NumPy for array operations
      import numpy as np

      data = np.array([1, 2, 3, 4, 5])
      result = np.sum(data)
      ```

19. **Inline Operations**:
    - Use inline operations instead of function calls for simple operations within loops.
    - Example:
      ```python
      # Inline operations
      total = 0
      for item in my_list:
          total += item
      ```

20. **Avoiding Global Variables**:
    - Minimize the use of global variables as they can lead to performance overhead and make code harder to maintain.
    - Example:
      ```python
      # Avoiding global variables
      def my_function():
          local_var = 42
          # Use local_var instead of a global variable
      ```

21. **Using Set Operations**:
    - Utilize set operations for efficient membership tests and set arithmetic.
    - Example:
      ```python
      # Using set operations
      set1 = {1, 2, 3, 4}
      set2 = {3, 4, 5, 6}
      intersection = set1 & set2
      ```

22. **Using List Comprehensions**:
    - Employ list comprehensions for concise and efficient creation of lists.
    - Example:
      ```python
      # Using list comprehensions
      squares = [x**2 for x in range(10)]
      ```

23. **Generator Expressions**:
    - Use generator expressions to lazily compute values and conserve memory.
    - Example:
      ```python
      # Generator expression
      gen = (x**2 for x in range(10))
      ```

24. **String Formatting**:
    - Opt for efficient string formatting methods like f-strings or `str.format()` over concatenation for improved readability and performance.
    - Example:
      ```python
      # Efficient string formatting
      name = "John"
      age = 30
      formatted_string = f"Name: {name}, Age: {age}"
      ```

25. **Memoization**:
    - Implement memoization to cache the results of expensive function calls and avoid redundant computations.
    - Example:
      ```python
      # Memoization
      cache = {}

      def fib(n):
          if n in cache:
              return cache[n]
          if n <= 1:
              return n
          result = fib(n-1) + fib(n-2)
          cache[n] = result
          return result
      ```

26. **Concurrency**:
    - Utilize concurrent programming techniques such as threading or multiprocessing to execute multiple tasks concurrently and improve performance, especially in I/O-bound scenarios.
    - Example:
      ```python
      # Concurrency with threading
      import threading

      def worker():
          # Task execution here
          pass

      threads = []
      for _ in range(5):
          t = threading.Thread(target=worker)
          threads.append(t)
          t.start()

      for thread in threads:
          thread.join()
      ```

27. **Profile and Optimize**:
    - Profile your code using tools like cProfile to identify bottlenecks and optimize accordingly.
    - Example:
      ```python
      # Profiling code
      import cProfile

      def my_function():
          # Function implementation here
          pass

      cProfile.run('my_function()')
      ```

28. **Using Caching Libraries**:
    - Employ caching libraries like `functools.lru_cache` for automatic memoization and caching of function results.
    - Example:
      ```python
      # Using functools.lru_cache
      from functools import lru_cache

      @lru_cache(maxsize=None)
      def fib(n):
          if n <= 1:
              return n
          return fib(n-1) + fib(n-2)
      ```

29. **Using `collections.defaultdict`**:
    - `defaultdict` from the `collections` module allows you to define default values for missing keys in dictionaries, which can be faster than using `dict.setdefault()`.
    - Example:
      ```python
      from collections import defaultdict

      # defaultdict usage
      d = defaultdict(int)
      d['a'] += 1  # No need to check if 'a' exists
      ```

30. **Avoiding `global` Keyword**:
    - Minimize the use of the `global` keyword in functions as it can lead to slower performance due to global variable lookups.
    - Example:
      ```python
      # Avoiding global keyword
      def increment_counter():
          global counter  # Less efficient
          counter += 1

      def increment_counter(counter):  # Better approach
          return counter + 1
      ```

31. **Leveraging `map()` and `filter()`**:
    - Utilize `map()` and `filter()` functions for efficient iteration and filtering over large datasets compared to list comprehensions.
    - Example:
      ```python
      # Using map() and filter()
      numbers = [1, 2, 3, 4, 5]
      doubled = list(map(lambda x: x * 2, numbers))
      evens = list(filter(lambda x: x % 2 == 0, numbers))
      ```

32. **Avoiding `len()` in Loops**:
    - Cache the length of sequences outside the loop to avoid calling `len()` repeatedly, which can improve performance, especially for large collections.
    - Example:
      ```python
      # Avoiding len() in loops
      items = [1, 2, 3, 4, 5]
      length = len(items)
      for i in range(length):
          # Loop body
          pass
      ```

33. **Using `itertools` Module**:
    - Leverage functions from the `itertools` module for efficient iteration, combination, and permutation operations.
    - Example:
      ```python
      from itertools import combinations

      # itertools usage
      combos = combinations([1, 2, 3], 2)
      ```

34. **Using Bitwise Operators for Flags**:
    - Represent multiple boolean flags using bitwise operations (`&`, `|`, `^`) for compactness and potentially improved performance.
    - Example:
      ```python
      FLAG_A = 1
      FLAG_B = 2
      FLAG_C = 4

      # Bitwise flags
      flags = FLAG_A | FLAG_C
      ```

35. **Prefer Built-in Functions Over Custom Implementations**:
    - Utilize built-in functions and methods whenever possible as they are often optimized for performance.
    - Example:
      ```python
      # Using built-in functions
      max_value = max(numbers)
      ```

