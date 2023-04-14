# Map and Filter in Python 3 
## The Map Function

### The idea of a map function is to apply a function to an **iterable** data. 

#### How the formatting looks like: ```map(function_name, sequence)``` 
  1. ```function_name``` --> any function (built-in or selfmade) that returns a desired value of choice. 
  2. ```sequence``` --> any iterable data type. 

```python 
# Example 1 
def square(num):
    ''' squares the given num argument '''
    return num ** 2
# end of square

array = list(range(1,11))
square_array = list(map(square, array))

print('Original Array:', array)
print('Array Squared:', square_array)
# Output of Original Array: [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
# Output of Array Squared: [1, 4, 9, 16, 25, 36, 49, 64, 81, 100]
```
### Important note: 
- The map function does not return a specfic data type, but returns a python iterable data. Therefore, after applying the map function, we execute a list function on it
```python
# Example 2

def upper(x):
    ''' upper() turns string x into its uppercased counter part '''
    return x.upper()

word = 'hello world!'
upper_word = ''.join(list(map(upper, word)))

print(word)
print(upper_word)

# simpler way:
print(word.upper())

# Outputs

# hello world!
# HELLO WORLD!
# HELLO WORLD!
```
### What is happening in this example? 
  * Example 2 showcases lot of unnecessary work in order to make the original word variable uppercased. This is key example of how you shouldn't use ```map()``` for every little change you want to a string.
  * This also applies to all data structures that have methods. You don't want to use methods with map, since theres already a method you might want to use. 

## Filter Function

### The idea of the filter function is to filter out items from a data set that meets a certain condition 
#### How formatting looks like: ```filter(bool_returning_function, sequence) 
  1. ```function``` --> The function name we provide for ```filter()``` must be a return boolean value.
  * It should also be able to handle the items inside the sequence as it's arguements. 
  2. ```sequence``` --> Any iterable data type. 

```python 
# Example 3

def isOdd(x):
    ''' isOdd() returns True if x is odd.'''
    return x % 2 != 0

array = list(range(1,101))
odds = list(filter(isOdd, array))

print('Odd Numbers from 1 to 100:', odds)
# Output: Odd Numbers from 1 to 100: [1, 3, 5, 7, 9, 11, 13, 15, 17, 19, 21, 23, 25, 27, 29, 31, 33, 35, 37, 39, 41, 43, 45, 47, 49, 51, 53, 55, 57, 59, 61, 63, 65, 67, 69, 71, 73, 75, 77, 79, 81, 83, 85, 87, 89, 91, 93, 95, 97, 99]
```
#### This could have been done different but this was a simple use of filter to show you can ___filter___ out variables that satisfies condition (True).

## Example Problem: List of Palindromic Numbers 
### The goal in this example is to create a list of palindromic numbers from 1 to 10000
```python
# Palindromic Numbers from 1 to 10000

def isPalindrome(x):
    ''' isPalindrome returns True if string X is a palindrome.'''
    return x == x[::-1]

array = list(range(1,10000))

palindromic_numbers = list(map(int, filter(isPalindrome, map(str, array))))
print('Palindromic Numbers from 1 to 10,000', palindromicNumbers)
Output: Palindromic Numbers from 1 to 10,000 [1, 2, 3, 4, 5, 6, 7, 8, 9, 11, 22, 33, 44, 55, 66, 77, 88, 99, 101, 111, 121, 131, 141, 151, 161, 171, 181, 191, 202, 212, 222, 232, 242, 252, 262, 272, 282, 292, 303, 313, 323, 333, 343, 353, 363, 373, 383, 393, 404, 414, 424, 434, 444, 454, 464, 474, 484, 494, 505, 515, 525, 535, 545, 555, 565, 575, 585, 595, 606, 616, 626, 636, 646, 656, 666, 676, 686, 696, 707, 717, 727, 737, 747, 757, 767, 777, 787, 797, 808, 818, 828, 838, 848, 858, 868, 878, 888, 898, 909, 919, 929, 939, 949, 959, 969, 979, 989, 999, 1001, 1111, 1221, 1331, 1441, 1551, 1661, 1771, 1881, 1991, 2002, 2112, 2222, 2332, 2442, 2552, 2662, 2772, 2882, 2992, 3003, 3113, 3223, 3333, 3443, 3553, 3663, 3773, 3883, 3993, 4004, 4114, 4224, 4334, 4444, 4554, 4664, 4774, 4884, 4994, 5005, 5115, 5225, 5335, 5445, 5555, 5665, 5775, 5885, 5995, 6006, 6116, 6226, 6336, 6446, 6556, 6666, 6776, 6886, 6996, 7007, 7117, 7227, 7337, 7447, 7557, 7667, 7777, 7887, 7997, 8008, 8118, 8228, 8338, 8448, 8558, 8668, 8778, 8888, 8998, 9009, 9119, 9229, 9339, 9449, 9559, 9669, 9779, 9889, 9999]
```
### Explanation of the code: 
#### Function Composition Breakdown:
  1. String version of the array --> ```map(str, array)```
  2. Filter out the palindrome --> ```filter(isPalindrome, string version of the array)```
  3. Remap all values back to integers --> ```map(int, palindromes)```
  4. Turn the mapped integers iterable back inside a list --> ```list(palindromicIterables)```

### How it would look like with multiple defined variables: 
```python
array = list(range(1,10000))
str_array = map(str, array)
palindromes = filter(isPalindrome, str_array)
palindromics = map(int, palindromes)

palindromic_numbers = list(palindromes)
```
## Composition of Functions
### What is it?
  * _Composition of Functions_ is the idea of using functions with a function call or apply one to the results of another function.
  * Read about it [here](https://en.wikipedia.org/wiki/Function_composition) or something 

