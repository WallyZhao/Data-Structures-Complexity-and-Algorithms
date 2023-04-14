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
    * There's too many examples to list over, just refer to [note](https://mrparkonline.github.io/courses/datastruct/sets/) 😭
## Disjoint: A Set Behaviour Property
### Two sets are considered disjointed when two sets share no common value. 

 * Let A and B both represent a set. 
 * If A & B is empty, then set A and B are considered disjointed.
 * To check this in python there is a method called: ```isdisjoint()```

## Set Operators as Methods
 * Yeah you can do this, refer to [note](https://mrparkonline.github.io/courses/datastruct/sets/)

## Assignment Operation & Updating Methods
 * This is a way to affect an orginal set with another and assign the result back to the original set... [note](https://mrparkonline.github.io/courses/datastruct/sets/)

## Set Comprehension 
 * IT'S THE SAME AS LIST COMPREHENSION... LOOK!!!
```python
# Set Comprehension Example
def isPalindrome(x):
    ''' isPalindrome() returns True if string X is a palindrome '''
    return x == x[::-1]

nums = list(range(1,10000))
palindromic_set = {num for num in nums if isPalindrome(str(num))}

print('Palindromic Numbers Set from 1 to 10000:')
print(palindromic_set)

# Output 
Palindromic Numbers Set from 1 to 10000:
{1, 2, 3, 4, 5, 6, 7, 8, 9, 515, 11, 6666, 525, 9229, 1551, 4114, 22, 535, 33, 545, 5665, 8228, 3113, 555, 44, 9779, 565, 55, 4664, 7227, 575, 2112, 66, 585, 8778, 77, 3663, 6226, 595, 1111, 88, 606, 7777, 99, 101, 2662, 616, 5225, 111, 626, 6776, 121, 9339, 636, 1661, 4224, 131, 646, 141, 5775, 656, 8338, 151, 3223, 666, 161, 9889, 676, 4774, 7337, 171, 686, 2222, 181, 696, 8888, 3773, 191, 6336, 707, 1221, 202, 717, 7887, 212, 2772, 727, 5335, 222, 737, 6886, 232, 9449, 747, 1771, 4334, 242, 757, 252, 5885, 767, 8448, 3333, 262, 777, 9999, 272, 787, 4884, 7447, 282, 2332, 797, 292, 8998, 808, 3883, 6446, 303, 9009, 818, 1331, 313, 828, 7997, 2882, 323, 5445, 838, 8008, 333, 848, 6996, 343, 9559, 1881, 858, 4444, 7007, 353, 868, 363, 5995, 878, 8558, 3443, 373, 6006, 888, 383, 898, 4994, 7557, 393, 2442, 909, 5005, 404, 919, 3993, 6556, 414, 9119, 929, 1441, 4004, 424, 939, 2992, 434, 5555, 949, 8118, 3003, 444, 959, 9669, 454, 1991, 969, 4554, 7117, 464, 2002, 979, 474, 8668, 989, 3553, 484, 6116, 999, 1001, 494, 7667, 2552, 505, 5115}
```
## Ending notes for Sets 
 * Sets aren't sliceable or indexable
 * Sets cannot been nested in a set 
 * Sets do not have order
 * Sets cannot guarantee that their values will be in order
 * Sets do not record a value's position
 


