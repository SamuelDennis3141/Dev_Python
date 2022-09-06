# Python Fundamentals

## Variables

Values can be assigned to objects called variables.

In Python the syntax to set a variable is:

`test = 5`

This stores the number 5 inside the variable called 'test'

You can then perform methods on variables which can perform actions on them or tell you more about the variable. As an example we can see the type of data structure/type which is stored in the 'test' variable by executing the following.

`print(type(test))`

This will return: `<class 'int'>`

This tells us that this has the integer data type.

You can store any data type or data structure inside of a variable.

You can also prompt the user of the program to assign a value to a predefined variable using:

`name = input("What is your name? ")`

## Data Types

Python has the following data types built-in by default, in these categories:

- Text Type:	`str`
Strings can contain any characters and convert them into a text format

- Numeric Types:	`int`, `float`, `complex`
Ints are whole numbers, floats are decimals, complex are complex numbers (where the imaginary part is denoted by j e.g: 1 + 2j)

- Sequence Types:	`list`, `tuple`, `range`
See data structures

- Mapping Type:	`dict`
See data structures

- Set Types:	`set`
Sets are lists which contain only unique values

- Boolean Type:	`bool`
Contain True or False values

Each of these data types have their own methods which can be found in their documentation.

### F Strings

You can format strings by using f-strings allowing you to directly write variables into a string.
```
name = Sam
print(f"Hello {name}!")  # returns Hello Sam!
```
## Data Structures

### What are Lists?
- correct syntax []
- lists are mutable
- indexing applies

Example:
```python
shopping_list = ["bat", "bread", "milk"]
print(shopping_list[0])
print(len(shopping_list))
print(type(shopping_list))

# how to add to a list
shopping_list.append("oreos")  # append() adds item to the end of the list
print(shopping_list)

# how to delete an item from a shopping list
shopping_list.remove("milk")
print(shopping_list)

# how to replace item in shopping list
shopping_list[0] = "milk"

# slice list
mixed_list = [1, 2, 3, "one", "two", "three"]
print(mixed_list[1:3])  # outcome would be [2, 3] [start point (inclusive): end point (exclusive): step size]
```
### What are Tuples?

- correct syntax: ()
- tuples are immutable
- use cases are for when you dont want to change the contents of the collections

Example:
```python
 essential = ("city", "DOB", "place of birth")
 print(essential)  
 print(type(essential))
 print(essential[1])
```
### What is a dictionary?
- use key value pairs
- dictionary can have all types of data collections
- syntax for dictionaries {key:value}

Example:
```
devops_student_1 = {"name": "sam",
                    "age": 21,
                    "stream": "tech",
                    "completed_lessons": 3,
                    "completed_lessons_names": ["strings", "lists", "operations"]
                    }
print(devops_student_1.keys())
print(devops_student_1.values())
print(devops_student_1["completed_lessons_names"][1])
# find out how to delete an item from dictionary and delete operations
# find out how to change completed lessons from 3 to 2
del(devops_student_1["stream"])  # use the del command to delete an item from a dictionary
devops_student_1["completed_lessons"] = 2  # you can reassign using the index

# you can reassign embedded lists
devops_student_1["completed_lessons_names"][1] = "sparta skills"  
print(devops_student_1)
```

## Operators

There are two types of operators arithmetic operators and comparison operators.

### Arithmetic Operators:

- `+` add
- `-` subtract
- `/` divide
- `*` multiply
- `**` exponent
- `%` returns remainder

#### Examples

```python
print(5 + 4)  # returns 9
print(5 - 4)  # returns 1
print(5 / 4)  # returns 1.25
print(5 * 4)  # returns 20
print(5 ** 4)  # returns 625
print(9 % 4)  # returns 1 (because 9/4 is equal to 2 remainder 1 and it gives the remainder)
```

### Comparison Operators:

These operators return boolean values aka True or False when comparing two operands.

- `>` greater than
- `<` less than
- `==` equal to
- `!=` not equal to
- `<=` less than or equal to
- `>=` greater than or equal to

#### Examples

```python
print(5 > 4)  # returns True
print(5 < 4)  # returns False
print(5 == 4)  # returns False
print(5 != 4)  # returns True
```

## Control Flow

Control flow is used to simply control the flow of the program. Sometimes you only want to execute parts of the code if certain conditions are met. This can be done through control flow methods.

### If Else Blocks

An if statement operates by using comparison operators. If the condition (or comparison) returns True then the following indented block is executed. If the condition is not true then the next block will be executed which could be either an: `elif` block, `else` block or nothing at all. The elif block also contains a condition but the else block is only executed if no other conditions are met.

Example:
```
a = 33
b = 200
if b > a:
  print("b is greater than a")
elif b < a:
  print("b is less than a")
else: 
  print("It is neither greater than or less than, so it must be equal to!")
```

### Try Except Blocks
When an error occurs, or exception as we call it, Python will normally stop and generate an error message.

These exceptions can be handled using the try statement:

```
try:
  print(name)
except:
  print("An exception occurred")
```

## Loops

You can use loops to iterate through sequences, or repeat tasks in order to prevent the developer from repeating themselves.

### For loops

For loops are used to iterate through sequences by executing for every item in the list. The block which will be iterated through should be indented.

Example:

```python
people = ["Sam", "Peter", "Joseph", "James"]
for person in people:
  print(person)
```

returns:
```
Sam
Peter
Joseph
James
```

### While loops

While loops continue whilst a specific condition is true. They can be used to loop indefinitely (mainly used until a specific condition is met as to not crash the program).

Example:
```python
x = 0
while x < 10:
  x += 1  # adds 1 to the x variable
```

## Functions

A function is a block of code which only runs when it is called. You can pass data, known as parameters, into a function. A function can return data as a result.

### Creating a Function

You can create a function using the following syntax `def FUNCTION_NAME(ARGUMENTS):` The function code should be indented. 

```python
def add_five(x):
  return x + 5
```

Calling the function

```
print(add_five(5))  # returns 10
```
