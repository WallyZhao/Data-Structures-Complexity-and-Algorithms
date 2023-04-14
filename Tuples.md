# Tuples in Python 3 

## What are Tuples? 
### Tuples are involved with Strings and Lists as they are the most basic iterable data type, with similar key differences 
  * Strings only allow alphanumeric characters and special symbols to represent text
  * Lists allow all data types as items/members
  * Strings are **immutable**, whereas Lists are **mutable**
  
### These differences cause a headache when you are rewuired the following data structure: 
  * It must immutable
  * It must allow different datatypes as items
  * It must be iterable
  * It must be nestable (List within a list, for loop within a for loop, etc...) 

### All of these are solved with the data struture called: ___Tuple___

## How to use Tuples in Python 3 
  * Tuples are declared with bracekts... **round ones**
  * ```()``` is an empty Tuple
  * ```(50,)``` is a singleton Tuple; yse the comma is required
  * Tuples are sliceable; therefore, indexable using **square brackets**
#### A singleton is an iterable data structure with only single item. 

## Tuple Example 1 
```python
tup = ('C', ' Java', 'Python')
empty_tup = ()
single_tup = ('Park',)

print(tup)
print(empty_tup)
print(single_tup)

# Outputs

# ('C', ' Java', 'Python')
# ()
# ('Park',)
```

## Tuple Operators
```python
# Concatenation: Joining two tuples
a = (1,2,3)
b = (4,5,6)
concat_result = a + b
print('a+b:', concat_result)


# Repetition: Repeating a list multiple times
c = ('Hi!',)
repet_result = c * 3
print('c*3', repet_result)

# Membership: Check if a value exists in a tuple
d = a + b + c
print('d:', d)
print('\'Hi!\' in d:', 'Hi!' in d)
print('7 in d:', 7 in d)

# Outputs 

# a+b: (1, 2, 3, 4, 5, 6)

# c*3 ('Hi!', 'Hi!', 'Hi!')

# d: (1, 2, 3, 4, 5, 6, 'Hi!')

# 'Hi!' in d: True

# 7 in d: False
```

## Tuples are Iterable, Indexable, and Sliceable. 
```python
# Iteration
example = ('C', 'Java', 'Python', 'C#', 'JavaScript')

print('Tuple example items:')
for language in example:
    print(language)
print('--')

# Indexing
print('Index 1:', example[1])
print('Last Value:', example[-1])

# Slicing
print('Backwards:', example[::-1])
print('Every other:', example[::2])
print('From 1 to end:', example[1:])
print('From 1 to 3:', example[1:3])
```
### Tuple example items: 
  * C
  * Java
  * Python
  * C#
  * JavaScript
```python
Index 1: Java
Last Value: JavaScript
Backwards: ('JavaScript', 'C#', 'Python', 'Java', 'C')
Every other: ('C', 'Python', 'JavaScript')
From 1 to end: ('Java', 'Python', 'C#', 'JavaScript')
From 1 to 3: ('Java', 'Python')
```
## Built-in Functions with Tuple
  * It's the same thing with Strings and Lists (Refer to Mr. Park's [Note](https://mrparkonline.github.io/courses/datastruct/tuples/))

## Tuple Comprehension
```python
# Tuple of Even values from 1 to 100
even_tup = tuple(i for i in range(1,101) if i % 2 == 0)

print(even_tup)
```
  * Same general format as List Comprehension
  * Except the brackets were taken for a different functionality in python, so it has to be formatted like this. 

## Tuple & Python: Packing and Unpacking
```python
# Examine the following code

# Packing
var_1 = 2
var_2 = 3
var_3 = 5

prime = var_1, var_2, var_3

print('Packed prime values:', prime)

# Unpacking and Repacking
fib = (0, 1, 1, 2, 3, 5, 8)

fib_0, fib_1, fib_n = fib[0], fib[1], fib[2:]
print('fib_0:', fib_0)
print('fib_1:', fib_1)
print('fib_n:', fib_n)

# Outputs

# Packed prime values: (2, 3, 5)
# fib_0: 0
# fib_1: 1
# fib_n: (1, 2, 3, 5, 8)
```
### How does this work?
  * Packing collect multiple variable's values and assign it to a single variable
  * Unpacking helps us to assign certain values from a tuple to different variables 
  * This becomes a **very useful** skill when combined with variable arguments for **Function Defintion** and **Function Calls**

