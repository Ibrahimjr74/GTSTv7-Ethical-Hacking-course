- Indexing and slicing{start,stop,step}
- Input handling(2 methods)
- Operations
- indentation
- if else
- Errors(Exceptions)
- Error handling
- loops

# Indexing
## Indexing in Python: A Comprehensive Guide
Indexing in Python refers to the process of accessing specific elements within a sequence, such as a string, list, or tuple, using their positions. Python employs zero-based indexing, meaning the first element has an index of 0, the second has an index of 1, and so on.
### Basic Indexing

To access an element, use square brackets `[]` with the desired index:

Python

```
my_list = [10, 20, 30, 40, 50]
my_string = "Hello, World!"

# Accessing elements
first_element = my_list[0]  # Output: 10
third_character = my_string[2]  # Output: 'l'
```

### Negative Indexing

You can also access elements from the end of a sequence using negative indices:

Python

```
# Accessing elements from the end
last_element = my_list[-1]  # Output: 50
second_last_character = my_string[-2]  # Output: 'd'
```

### Slicing

Slicing allows you to extract a portion of a sequence:

Python

```
# Slicing a list
Mylist[start:stop:step]
sublist = my_list[1:4]  # Output: [20, 30, 40]
# Slicing a string
substring = my_string[7:12]  # Output: 'World'
name=['ethiopia','banana','china','apple']
print(name[-1:0:-2])
#Output: ['apple','banana']
```

- `start_index` (inclusive): The index where the slice begins.
- `end_index` (exclusive): The index where the slice ends (not included).
- You can omit the start index to default to the beginning.
- You can omit the end index to default to the end.

### Common Use Cases

- **Extracting elements:** Accessing specific values from lists, tuples, or strings.
- **Modifying elements:** Changing values in mutable sequences like lists.
- **Iterating over elements:** Using indices to control loops.
- **Searching for elements:** Finding positions of specific values.
- **Slicing:** Creating subsets of sequences.

### Example: Finding the Index of an Element

Python

```
numbers = [2, 5, 8, 1, 9]
index_of_5 = numbers.index(5)  # Output: 1
```

### Important Considerations

- **IndexError:** Trying to access an element with an index out of bounds raises an `IndexError`.
- **Immutability:** Strings and tuples are immutable, meaning their elements cannot be changed after creation.
- **Negative indices:** Can be used for flexible access from the end of the sequence.

## User Input handling
- On Python there are 2 types of inputs
A) By user input example
```
name= input('what is your name')
print(f"Welcome{name})

number = input("Enter number:")
print(type(number))

number = int("Enter number:")
print(type(number))

number = eval("Enter number:")
print(type(number))

```
B) By  argument 

- This help us to get the input from the command lines
- Shell: python gtst.py arg1 arg2 arg3
- Syntax:
```
    import sys
    name = sys.argv[1]
    print(f"Hello{name}!")
```

  **![](https://lh7-rt.googleusercontent.com/slidesz/AGV_vUdNVd8uL8KrLhoHRvzU5lpJZXvE8qCSmK2aawW5uacCAjDJstHi5CP037aX7aVAwnEyiNeWNlOTlBP-P38yInJR2y5v-SM4StmaBm8t5-CU17-o_vhdbeRUPI9Fpb0xrma7Rvn7SVRMoji3p6IVxf4kUdhkYqlR=s2048?key=5D-mzvmy1PfnlzqCK562Dg)**


**
##Operators
**

- Operators are special symbols that perform operations on variables and values. For example,
    
- There are lots of operators type on python:
1. Arithmetic operators
2. Assignment Operators
3. Comparison Operators
4. Logical Operators
5. Bitwise Operators
6. Special Operators
    
 More on Bitwise Operation


- There are 
- Compliment ( Not) (~)  
**![](https://lh7-rt.googleusercontent.com/slidesz/AGV_vUe-HQXkwjy1oXNHOTZzWLzui53oepm1V8tDmZSgNYhKlkPx3Ig4eVNsZI1zH52QgqU3JaZnvthT1AAnCEU2xuzX5E1vyP1PUBGuQiMrvaTFrl6Ew28GVM5g4HOBKEGozwv2MbdFY8eMcqyv0jyq9BAPe5ZG8l4=s2048?key=5D-mzvmy1PfnlzqCK562Dg)**
- And ( & )    
**![](https://lh7-rt.googleusercontent.com/slidesz/AGV_vUc9VH9MDL-6MlQLWKwdNqlTBBZ9dBJKr0dlfvShvCsIaqpK2FFoYs7ONLTLzwwv30dMzP11Em9OlMToOSQJAuJiVHIlVHFs2KJV0xREE05fh8Tdo8oZCZ-kPmXUH0jLBKDlsKffrOhgw6LCiVsp4JMatGKnQIc=s2048?key=5D-mzvmy1PfnlzqCK562Dg)**
- Or ( | )    
**![](https://lh7-rt.googleusercontent.com/slidesz/AGV_vUcF9MQ8hTY-eWqbMQJAVYd9lCzB_eze4kyYxEdhPME-tSXk1LPI0MIIo4SiebLuGXmLkKNcf8-hKNYVDWakDgUc67g9Zw8DuSD62eolPMMnRnV-X8S5qcRL4xawCXYc5r_dxiSZnb4x3i48dz4LnwfKOsnsGbFP=s2048?key=5D-mzvmy1PfnlzqCK562Dg)**
- Xor ( ^ )  
 **![](https://lh7-rt.googleusercontent.com/slidesz/AGV_vUcQ0aUWUB0HuqcMq7uURQ0FvJOFmu1khH7ePLvBMhXHTz4Ax6gtbYvin38VS98YJk2ZlO47hQA-oalu4v9YpWchscQrYRZBVx-N3AtDrOs0fmqV5FwRCNo8J-ESLVEeUTmuH9pE0y_Sp36F7uuTyOES2t84sqeY=s2048?key=5D-mzvmy1PfnlzqCK562Dg)**
- Left Shift (<<) 
**![](https://lh7-rt.googleusercontent.com/slidesz/AGV_vUcUWAv65KVCvX17iFfh3VeMuRqxGnbyQUcZq1lEf10JBrwTmRZmKRWux6dv27BaGmZP0YCrcYrFv873chGhqeN540dACAxv7rUIqE3CYPvjXh6KDQ_UCLeZ-5DYkMvfK3PX1JEiSY8c2ym94xyzi0_M1iPgsneB=s2048?key=5D-mzvmy1PfnlzqCK562Dg)**
- Right shift (>>)
-**![](https://lh7-rt.googleusercontent.com/slidesz/AGV_vUdbBNkxQJ6-Jmqjyg4r6u3mYDR2RoAwgplYiFdPNKng2igV8c-dLa-vxiHXEPkwWZOtjgu0Xe3Vo4dC-_MWielF55PlgF_z-fDTt6UYHGxb7uyI2zamPKx87tdb8oooVeE28FLbPYACDT6-mMoklgjz-5LcqLiv=s2048?key=5D-mzvmy1PfnlzqCK562Dg)**
    
## Identations 

- Are white spaces that python uses for  function

## if-else
- **Conditional execution:** Chooses which code block to run based on a condition.
    - `if condition:`
        - Code to execute if condition is True
    - `else:`
        - Code to execute if condition is False
- Indentation is crucial for defining code blocks.

## Errors (Exceptions)

- **Unexpected events:** Occur during program execution, disrupting normal flow.
- **Types:** Syntax errors (invalid code), runtime errors (errors during execution), logical errors (incorrect results).
- **Common exceptions:** `ZeroDivisionError`, `TypeError`, `ValueError`, `IndexError`, `FileNotFoundError`.

## Error Handling

- **try-except block:** Handles exceptions gracefully.
    - `try:`
        - Code that might raise an exception
    - `except ExceptionType:`
        - Code to handle the specified exception
    - `else:`
        - Code to execute if no exception occurs
    - `finally:`
        - Code to always execute, regardless of exception

## Loops

- **Repeated execution:** Execute a block of code multiple times.
- **for loop:** Iterates over a sequence (list, tuple, string, etc.).
    - `for item in sequence:`
        - Code to execute for each item
- **while loop:** Repeats as long as a condition is True.
    - `while condition:`
        - Code to execute while condition is True

## Additional Notes

- Combine `if-else` with loops for conditional execution within loops.
- Use error handling to prevent program crashes and provide informative messages.
- Choose the appropriate loop type based on the task.

**Example:**

Python

```
numbers = [1, 2, 3, 0, 5]

for num in numbers:
  try:
    result = 10 / num
    print(f"10 divided by {num} is {result}")
  except ZeroDivisionError:
    print(f"Cannot divide by zero for number {num}")
  else:
    print("Division successful")
  finally:
    print("This will always execute")
```