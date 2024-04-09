**Useful Tip: Working with `%` for Digit Operations**:

When working with digits, especially in competitive programming challenges involving numbers, the modulus operator `%` is incredibly handy for various tasks:

1. **Extracting Last Digit**: Use `n % 10` to extract the last digit of a number efficiently.
   ```python
   n = 12345
   last_digit = n % 10  # This will give 5
   last_two_digits = n % 100  # This will give 45
   ```

2. **Extracting Second Last Digit**: To extract the second last digit, use `(n // 10) % 10`.
   ```python
   n = 12345
   second_last_digit = (n // 10) % 10  # This will give 4
   ```

3. **Extracting Digits in Reverse Order**: Use `% 10` repeatedly in a loop to extract digits in reverse order.
   ```python
   n = 12345
   while n > 0:
       digit = n % 10
       print(digit)  # This will print digits from right to left: 5, 4, 3, 2, 1
       n //= 10
   ```

4. **Checking Even or Odd**: Use `n % 2` to check if a number is even or odd.
   ```python
   n = 10
   is_even = n % 2 == 0  # This will be True
   ```

5. **Reversing a Number**: To reverse a number, use the modulus operator in combination with integer division.
   ```python
   n = 12345
   reversed_number = 0
   while n > 0:
       digit = n % 10
       reversed_number = reversed_number * 10 + digit
       n //= 10
   ```

6. **Extracting First Digit**: Use a loop with `// 10` until the number becomes less than 10 to get the first digit.
   ```python
   n = 12345
   while n >= 10:
       n //= 10
   first_digit = n  # This will give 1
   ```

These `%` operations offer efficient solutions for various digit-related tasks in competitive programming challenges.

**Note:** In above examples use of `n // 10` is to remove last digit by using integer division.
