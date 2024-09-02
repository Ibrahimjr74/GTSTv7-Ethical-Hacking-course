## Functions
- A function is a block of code that performs a specific task
- let say we want to work on some thing like drawing circle
- we need : A function that create s function 
  with it's area, circumference, diameter...
  A function that creates a color function
  - There are two types of function in Python programming
  - Standard library function - These are built-in function in Python are available to use.
  - Ex - print() len() split() end() etc..
  - User defined often defined by the user
## Creating Functions
```
def function_name(arguments):
# function body

def greet():
print('Hello world'!)
# call the fuction 
greet()
# function with two arguments
def months(jan, march)
Mothersday = march
print('Happy Mothersday',Mothersday)
months(2,8)

```
  - Functions have to be called in order for the function works for intended purpose.
## Return in Python

- some times there may be return on python to return the values to the function and doesn't display upon calling. to do so we need to print the function
```
def add(x, y):
  return x + y

result = add(3, 4)
print(result)  # Output: 7

```
## Recursion
- is a process pf defining something in terms of itself. it is known that functions can call other functions. it is also possible for function call it  self.
### Advantage of Recursion
1. make the code look clean and elegant
2. reduces effort

Disadvantages of Recursion
- takes time and processors speed
## Anonymous /lambda Function

- if function doesn't have name it is called lambda function/ Anonymous
- if you have 1 line code to return you don't need to def a function
- a lambda function is a special type of function without the function name
- we use lambda instead of def
- Filter function
```
def is_even (n):
return n%2==0

nums=[3,2,6,8,4,6,2,91]

evens= list(filter(is_even,nums))
print(evens)

#using lambda
evens= list(filter(Lambda n:n%2==0, nums))
print(evens)
```
## Lambda, Filter, and Map in Python

### Lambda Functions

- **Anonymous functions:** Small, unnamed functions defined using the `lambda` keyword.
- **Syntax:** `lambda arguments: expression`
- **Purpose:** Used for short, simple functions that are needed only once.

**Example:**

Python

```
add = lambda x, y: x + y
result = add(3, 4)
print(result)  # Output: 7
```

### Filter Function

- **Creates a new iterable:** Contains elements from an iterable for which a given function returns True.
- **Syntax:** `filter(function, iterable)`
- **Purpose:** Used to filter elements based on a condition.

**Example:**

Python

```
numbers = [1, 2, 3, 4, 5]
even_numbers = list(filter(lambda x: x % 2 == 0, numbers))
print(even_numbers)  # Output: [2, 4]
```

### Map Function

- **Creates a new iterable:** Applies a given function to each item of an iterable and returns an iterator.
- **Syntax:** `map(function, iterable)`
- **Purpose:** Used to apply a transformation to each element of an iterable.

**Example:**

Python

```
numbers = [1, 2, 3, 4, 5]
squared_numbers = list(map(lambda x: x * x, numbers))
print(squared_numbers)  # Output: [1, 4, 9, 16, 25]
```

### Interrelation

- **Lambda functions** are often used as the first argument to `filter` and `map` to provide concise and efficient filtering or mapping operations.
- **Filter** and **map** are higher-order functions that take other functions (like lambda functions) as arguments.
- **Combining them:** You can combine `filter` and `map` to perform complex data transformations in a single expression.

**Example:**

Python

```
numbers = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
even_squares = list(map(lambda x: x * x, filter(lambda x: x % 2 == 0, numbers)))
print(even_squares)  # Output: [4, 16, 36, 64]
```

## Object-Oriented Programming /OOP
- Python is an object oriented Programming. This means more thing in python are objects.
- Objects are anything which can have action and name
- Objects have attributes(properties) and methods(action or function)

## Python class
- Class is simply a place where we create our Object's attribute and behavior
- a class is a blueprint for that object
-  Example attribute: name : Toshiba,hp,dell..
                 cpu : amd-ryzen,core i5
                 Use: for Coding, gaming,l istening music
## Creating Objects
- You can Create many Objects based on1 class
```
My_computer = computer()
My_computer.name ="pc laptop"
My_computer.cpu = "Intel core i9"

#  creating another object
Alemayew Computer = computer()
Alemayew Computer.name = "Dell Inspirion"
Alemayew Computer.cpu = "Intel core i3"

print(f"My_computer computer is called{Computer.name}")

```
## Giving Behaviors == Creating Methods

- Functions are called methods an OOP
```
class human:
name = ""
age = ""
grade = ""

def run(self):
  print("i can run")
def dance(self):
  print("I can dance)
def sleep(self):
  pirnt("i love to sleep)

ibro = human()
ibro.name = "ibrahim"
ibro.age = "23"
ibro.grade = "NG"

pirnt (ibro.name, human.sleep(ibro))
: : :
: : :
: : :

```

## python Constructor


**Constructors** are special methods in Python that are automatically called when an object of a class is created. They are used to initialize the object's attributes.

### Syntax:

Python

```
def __init__(self, parameters):
  # Initialize attributes
```

- `__init__`: This is the constructor method.
- `self`: It refers to the instance of the class.
- `parameters`: Optional parameters that can be passed when creating an object.

### Example:

Python

```
class Person:
  def __init__(self, name, age):
    self.name = name
    self.age = age

  def greet(self):
    print("Hello, my name is", self.name)

# Create    an object
person1 = Person("Alice", 30)

# Access attributes
print(person1.name)  # Output: Alice
print(person1.age)   # Output: 30

# Call a method
person1.greet()  # Output: Hello, my name is Alice
```

### Explanation:

1. We define a class named `Person` with a constructor `__init__` that takes `name` and `age` as parameters.
2. Inside the constructor, we assign the passed values to the object's attributes `self.name` and `self.age`.
3. We create an object `person1` of the `Person` class, passing "Alice" and 30 as arguments.
4. We access the object's attributes using dot notation.
5. We call the `greet` method on the object.

### Key Points:

- Constructors are essential for initializing object state.
- The `self` parameter is automatically passed to the constructor and refers to the instance being created.
- You can have multiple constructors by overloading, but it's generally not recommended in Python.
- Constructors can be used to perform other initialization tasks besides assigning attributes.
## Inheritance and Encapsulation in Python

### Inheritance

Inheritance is a fundamental concept in object-oriented programming (OOP) that allows you to create new classes (derived classes) by inheriting attributes and methods from existing classes (base classes). This promotes code reusability and hierarchical relationships between classes.  

**Example:**

Python

```
class Animal:
  def __init__(self, name):
    self.name = name

  def speak(self):
    pass  # Abstract method

class Dog(Animal):
  def speak(self):   
    print("Woof!")

class Cat(Animal):
  def speak(self):
    print("Meow!")

# Create objects
dog = Dog("Buddy")
cat = Cat("Whiskers")

dog.speak()  # Output: Woof!
cat.speak()  # Output: Meow!
```

**Key points:**

- The `Animal` class is the base class, providing a common blueprint.
- `Dog` and `Cat` are derived classes inheriting from `Animal`.
- The `speak` method is overridden in derived classes for specific implementations.

### Encapsulation

Encapsulation is the bundling of data (attributes) and methods that operate on that data within a single unit (class). It promotes data hiding and protects data integrity.  

**Example:**

Python

```
class BankAccount:
  def __init__(self, balance):
    self.__balance = balance  # Private attribute

  def deposit(self, amount):
    self.__balance += amount   
    print("Deposited:", amount)

  def withdraw(self, amount):
    if amount <= self.__balance:
      self.__balance -= amount
      print("Withdrawn:", amount)
    else:
      print("Insufficient funds")

  def get_balance(self):
    return self.__balance

account = BankAccount(1000)
account.deposit(500)
account.withdraw(200)
print(account.get_balance())  # Output: 1300
```

**Key points:**

- The `__balance` attribute is made private using double underscores.
- Methods like `deposit`, `withdraw`, and `get_balance` provide controlled access to the balance.
- Encapsulation protects data integrity by preventing direct modification of the balance.

### Combining Inheritance and Encapsulation

You can combine inheritance and encapsulation to create complex class hierarchies with data protection.

**Example:**

Python

```
class Shape:
  def __init__(self, color):
    self.__color = color

  def get_color(self):
    return self.__color

class Rectangle(Shape):
  def __init__(self, width, height, color):
    super().__init__(color)
    self.__width = width
    self.__height = height

  def    calculate_area(self):
    return self.__width * self.__height

# Create a rectangle object
rectangle = Rectangle(5, 10, "red")
print(rectangle.get_color())  # Output: red
print(rectangle.calculate_area())  # Output: 50
```

**Key points:**

- The `Rectangle` class inherits from the `Shape` class.
- The `Shape` class encapsulates the `color` attribute.
- The `Rectangle` class adds its own attributes and methods.
