# What is a Matrix? 

### Mathematically a **Matrix** is a representations of numbers, symbols, or expressions in a 2-Dimensional Array.
  * In Comp sci, especially with Python you can begin by creating a data structure with rows and columns, just like a table. 
## Mathematical diagram
   ![mathematical diagram](https://mrparkonline.github.io/figures/matrix_fig01.png) 
   
   * Row 1 would have the value of 1 2 3 4
   * Column 2 would have the value of 2 6 

# Coding a Matrix in Python 3
```python 
# Python 3 Representation of matrix A

matrix_A = [
    [1, 2, 3, 4],
    [5, 6, 7, 8]
]

# Accessing Matrix A
print('Row 1: %s' % matrix_A[0]) # Recall: Indexing starts at zero in Python
print('Value at Row 2 Column 2: %s' % matrix_A[1][1])
```
### There is no data structure called "Matrix" in Python so we have to create a list within a list 
#### It has to satisfy these conditions:
  1. All rows must have the same number of values
  2. All columns must have the same number of values
  3. All items in the 2D List must have the same data types
#### Since indexing always starts at 0 ... row 1 is technically located at matrix_A[0]

# List Comprehension in Python 3 

### List Comprehension is a concise method to create list in Python 3 

#### This technique is normally used when: 
  1. The list is a result of some operations applied to all its items
  2. It is a made from another sequence/iterable data
  3. The list is member of another list/sequence/iterable data that satisfies a certain condition
#### A lambda function would be used here, but we'll learn it when time comes 

## Old method
```python
# Old Method
squares = []
for i in range(10):
    squares.append(i ** 2)

print('Our result: %s' % squares)
# Our result: [0, 1, 4, 9, 16, 25, 36, 49, 64, 81]
```
## List Comprehension
```python
# List Comprehension

squares = [i**2 for i in range(10)]

print('Our new result: %s' % squares)
# Our new result: [0, 1, 4, 9, 16, 25, 36, 49, 64, 81]
```
## How does it actually work?

#### It consists of:
  1. A ***Square Bracket*** containing an expression that describes the list
  2. One or more ***For clause*** to explain its members
  3. Then a zero or more if clauses depending on the complexity of the list

## What is happening in the example?

#### In the List Comprehension example:
  1. ```i**2 for i in range(10)``` is the expression that describe the list
  2. ```i**2``` describes each item in the list
  3. ```i``` is taken from the for clause
  4. ```for i in range(10)``` describes where ```i``` comes from

## List Comprehension 2 
  * Creating a list within a list with two seperate lists by using List Comprehension
```python
# Solution
a = [1,2,3]
b = [3,1,4]

result = [[x, y] for x in a for y in b if x != y]
print(result)
# Output: [[1, 3], [1, 4], [2, 3], [2, 1], [2, 4], [3, 1], [3, 4]]
```
## How does this example work?

#### Each of items in the list has to be a list of two values so each item is described as ```[x, y]```
  1. x comes from a
  2. y comes from b
#### Also there is a condition to the item, ```x != y```
  * ```!=``` means "not". So as long as x does not equal y, the condition remains true. 
  * Which the adds the item described as ```[x, y]``` to the list. 

## List Comprehension 3 
  * Using List Comprehension to turn a 2D array called a 'vec' to a single list. 
 ```python
 # Solution

vec = [[1,2,3], [4,5,6], [7,8,9]]

result = [value for row in vec for value in row]
print('Vec as a single list of values: %s' % result)
# Output: Vec as a single list of values: [1, 2, 3, 4, 5, 6, 7, 8, 9]
 ```
 ## How does THIS example work?
 
 #### Vec is an example of a matrix in Python 3 by using a list within a list 
 
 #### In order to get value one by one you must do the following: 
  1. Explain what each item in the list comprehension is going to be ... in our case --> "value"
  2. To now access where value is, define where it comes from ... in our case --> "row"; therefore, for row in vec
  3. Finally we construct our last for clause to denote that value comes from the row

# With List Comprehension, the order of your For clauses MATTER
