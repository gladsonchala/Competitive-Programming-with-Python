# 5. Conditionals

Conditionals in Python allow you to make decisions based on whether certain conditions are true or false. They are essential for controlling the flow of your program.

---

### if Statement

The `if` statement is used to execute a block of code only if a specified condition is true.

```python
x = 10

if x > 5:
    print("x is greater than 5")
```

---

`Colon:` Don't forget the `:` colon symbol! It is used to separate conditions from the block of code just like braces `{}` in other languag.
The block of code is always indented after the `:` symbol!

---


### else Statement

The `else` statement follows an `if` statement and executes a block of code if the condition in the `if` statement is false.

```python
x = 3

if x > 5:
    print("x is greater than 5")
else:
    print("x is not greater than 5")
```

---

### elif Statement

The `elif` statement allows you to check multiple conditions. It follows an `if` statement and comes before the `else` statement.

```python
x = 5

if x > 5:
    print("x is greater than 5")
elif x == 5:
    print("x is equal to 5")
else:
    print("x is less than 5")
```

---

### Nested Conditionals

You can nest conditionals within each other to create more complex decision-making structures.

```python
x = 10
y = 20

if x > 5:
    if y > 10:
        print("x is greater than 5 and y is greater than 10")
    else:
        print("x is greater than 5 but y is not greater than 10")
else:
    print("x is not greater than 5")
```

---

### Logical Operators

Logical operators (`and`, `or`, `not`) can be used to combine multiple conditions.

```python
x = 10
y = 20

if x > 5 and y > 10:
    print("Both conditions are true")
else:
    print("At least one condition is false")
```

---

**1. Given three integers `x`, `y`, and `z`, write a Python program to find the largest among them without using the built-in `max()` function.**

<details>
<summary>Click to reveal solution</summary>

**Answer:**
```python
x = 10
y = 20
z = 15

if x >= y and x >= z:
    largest = x
elif y >= x and y >= z:
    largest = y
else:
    largest = z

print("The largest number is:", largest)
```
</details>

---

**2. Write a program to check whether the number is zero, positive, or negative.**

<details>
<summary>Click to reveal solution</summary>

**Answer:**
```python
def check_number(num):
    if num == 0:
        return "Zero"
    elif num > 0:
        return "Positive"
    else:
        return "Negative"

# Example usage:
num1 = 10
print(check_number(num1))  # Output: Positive

num2 = -5
print(check_number(num2))  # Output: Negative

num3 = 0
print(check_number(num3))  # Output: Zero
```
</details>

---

**3. Print "Summer" if the temperature in the city is greater than 32 degrees Celsius or the humidity index is more than 10.**

<details>
<summary>Click to reveal solution</summary>

**Answer:**
```python
def weather_conditions(temperature, humidity):
    if temperature > 32 or humidity > 10:
        print("Summer")
    else:
        print("Not Summer")

# Example usage:
temp1 = 35
humidity1 = 8
weather_conditions(temp1, humidity1)  # Output: Summer

temp2 = 28
humidity2 = 15
weather_conditions(temp2, humidity2)  # Output: Summer
```
</details>

---

**4. Write a program that takes a user's age as input and determines if they are eligible to vote (18 or older).**

<details>
<summary>Click to reveal solution</summary>

**Answer:**
```python
def check_voting_eligibility(age):
    if age >= 18:
        return "You are eligible to vote"
    else:
        return "You are not eligible to vote"

# Example usage:
user_age = int(input("Enter your age: "))
print(check_voting_eligibility(user_age))
```
</details>

---

**5. Write a program that takes a user's score as input and assigns a grade (A, B, C, D, or F) based on the following grading scale: A >= 90, B >= 80, C >= 70, D >= 60, F < 60.**

<details>
<summary>Click to reveal solution</summary>

**Answer:**
```python
def assign_grade(score):
    if score >= 90:
        return "A"
    elif score >= 80:
        return "B"
    elif score >= 70:
        return "C"
    elif score >= 60:
        return "D"
    else:
        return "F"

# Example usage:
user_score = int(input("Enter your score: "))
print("Your grade is:", assign_grade(user_score))
```
</details>

---

