# Print In Python and its hidden features

The `print()` function is a versatile tool in Python to output the datas and for debugging purposes. Let's explore various use cases beyond simple text printing:
---

**1. Print Multiple Items:**
   - You can print multiple items separated by commas.
   ```python
   name = "Gemechis"
   age = 21
   print("Name:", name, "Age:", age)
   ```
   Output:
   ```
   Name: Gemechis Age: 21
   ```

**2. Formatted String:**
   - Use f-strings to format and include variables directly in the string.
   ```python
   score = 95
   print(f"Your score: {score}%")
   ```
   Output:
   ```
   Your score: 95%
   ```

**3. Print to File:**
   - Redirect output to a file instead of the console.
   ```python
   with open("output.txt", "w") as f:
       print("Hello, file!", file=f)
   ```

4. **Print Without Newline:**
   - By default, `print()` adds a newline character. Use `end` parameter to change this behavior.
   ```python
   print("Hello, ", end="")
   print("world!")
   ```
   Output:
   ```
   Hello, world!
   ```

**5. Printing with Separator:**
   - Specify a separator between items in the `print()` function.
   ```python
   fruits = ["apple", "banana", "cherry"]
   print(*fruits, sep=", ")
   ```
   Output:
   ```
   apple, banana, cherry
   ```

**6. Print with Precision:**
   - Control the precision of floating-point numbers.
   ```python
   pi = 3.141592653589793
   print(f"The value of pi: {pi:.2f}")
   ```
   Output:
   ```
   The value of pi: 3.14
   ```

**7. Print with Escape Characters:**
   - Include special characters using escape sequences.
   ```python
   print("This is a line break.\nAnd this is a tab:\tHello!")
   ```
   Output:
   ```
   This is a line break.
   And this is a tab:    Hello!
   ```

**8. Printing Progress Bar:**
   - Create a progress bar to visualize the completion of a task.
   ```python
   import time

   def progress_bar(iteration, total, prefix='', suffix='', length=30, fill='█'):
       percent = ("{0:.1f}").format(100 * (iteration / float(total)))
       filled_length = int(length * iteration // total)
       bar = fill * filled_length + '-' * (length - filled_length)
       print(f'\r{prefix} |{bar}| {percent}% {suffix}', end='\r')
       if iteration == total:
           print()

   # Example usage:
   total_iterations = 100
   for i in range(total_iterations + 1):
       time.sleep(0.1)  # Simulate some task
       progress_bar(i, total_iterations, prefix='Progress:', suffix='Complete', length=50)
   ```

**9. Printing with Colors:**
   - Add colors to your terminal output for emphasis or readability.
   ```python
   class colors:
       HEADER = '\033[95m'
       OKBLUE = '\033[94m'
       OKGREEN = '\033[92m'
       WARNING = '\033[93m'
       FAIL = '\033[91m'
       ENDC = '\033[0m'
       BOLD = '\033[1m'
       UNDERLINE = '\033[4m'

   print(f"{colors.OKGREEN}Success!{colors.ENDC}")
   print(f"{colors.FAIL}Error!{colors.ENDC}")
   ```

**10. Printing ASCII Art:**
    - Display ASCII art for decorative or illustrative purposes.
    ```python
    print(r"""
         _______
        /       \
       /  🐍 🐍 🐍  \
      |   Python  |
       \         /
        \_______/
    """)
    ```

**11. Printing with Logging Module:**
    - Utilize the `logging` module for more advanced logging capabilities.
    ```python
    import logging

    logging.basicConfig(level=logging.INFO)
    logging.info("This is an informational message")
    ```

**12. Printing Unicode Characters:**
    - Display Unicode characters for internationalization or special symbols.
    ```python
    print("Currency symbols: €, ¥, £")
    ```

Experiment with these print() hacks to elevate your Python scripting to new heights!
