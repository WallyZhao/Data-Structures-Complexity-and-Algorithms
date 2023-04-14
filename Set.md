# Sets in Python 3 
## What is a set?
  * A Set is an unordered collection with no duplicate elements in Python 3. 
    1. Set is a mathematical way to describe collection of different unique objects. 
    2. By following the operations and characteristics of the mathematical set, we can utilize such data structure in our Python Code.
    3. The mathematical deinftion of set can be viewed [here](https://en.wikipedia.org/wiki/Set_(mathematics)) 

## Using Sets in Python 3 
### Defining a Set
```python 
# Set definition examples:
example_set1 = {1, 2, 3}
example_set2 = {'h','e','l','l','o'}

print('example_set1:', example_set1)
print('example_set2:', example_set2) # Notice there is only 1 'l'; Also notice the order of the values outputted
print('--')

singleton_set = {7}
empty_set = set() # this is because {} is reversed for a different feature in python 3.

print('Singleton:', singleton_set)
print('Empty Set:', empty_set)

# Outputs 
example_set1: {1, 2, 3}
example_set2: {'o', 'e', 'h', 'l'}
--
Singleton: {7}
Empty Set: set()
``` 
### Sets can also be used with basic built-in functions like Strings and Lists 
  * View Mr. Park's [Note](https://mrparkonline.github.io/courses/datastruct/sets/) for the examples

## Basic Membership Operators 
### Membership is one of the key operations with set for the following reasons: 
  * A set has no duplicates
  * The membership operation is one of the fastest operations compared to strings, lists, or tuples. We will learn more about this with the concept of "**complexity**"
  * By using membership, we can be certain a target exists or does not exist within the data 
 
```python
# Membership Example
example_set = set('hello')

print("Membership of: \'h\'", 'h' in example_set)
print("Non-Membership of: \'z\'", 'z' not in example_set)

# Outputs 
Membership of: 'h' True
Non-Membership of: 'z' True
```
## Accessing Values in a set
  * Due to the unordered nature of a set, there is no concept of indexing or slicing 
  * Sets are **iterable** though
```python
# Iteration of a Set
example_set = {2,3,5,7,11,13}

for v in example_set:
    print('Values of example_set:', v)
    
# Outputs 
Values of example_set: 2
Values of example_set: 3
Values of example_set: 5
Values of example_set: 7
Values of example_set: 11
Values of example_set: 13
```

## Python 3 Sets are mutable: Adding and Removing Values
  * Sets are mutable; therefore you can add and remove values 
  * Yeah I don't know anymore, refer to [note](https://mrparkonline.github.io/courses/datastruct/sets/) 

## Powering Up Sets: Set Operators 

  * Just like the mathematical counterpart, sets in Python 3 can utilize vast operators to help do complex calculations
  * Most of these operators have am ethod counterpart because sets are **mutable**

### The Operators 

  * Union - Joining/Combining two sets 
  * Intersection - Members/Items that can **only exist in both sets **
  * Difference - Members/Items that can **only exist in first set** and not **second set**
  * Symmetric Difference - Members/items that **exists one or the other set**, but **not both sets**
  * Proper Subset - Boolean operator
  * Subset - Boolean operator
  * Proper Superset - Boolean operator
  * Superset - Boolean operator
    * There's too many examples to list over, just refer to [note]((https://mrparkonline.github.io/courses/datastruct/sets/)) 😭
