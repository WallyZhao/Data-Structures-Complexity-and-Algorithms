# Dictionary in Python 3 
  * Dictionary (Associative Array, map, symbol table) is a data type that stores a collection of (key, value) pairs, such that each possible key appears at most once in the collection. 
## Common Operations:
  * Adding a pair
  * Removing a pair
  * Modifying an existing pair
  * Lookup of a value associated with a particular key
#
   _Aside_: This concept is an introduction to concepts similar to: hash table and search trees (???)
   
## Defining a Dictionary in Python 3
  * Dictionaries also use ```{}``` like sets; however, their individual item format is very different. 
  * Each item in a dictionary be a pair of ```key: value```
```python
# Dictionary Example
sammy = {
    'username': 'sammy',
    'online': True,
    'followers': 42
}

# There are 3 items: each with their unique addresses and value
# Accessing
print('Sammy dict:', sammy)
print('Username:', sammy['username'])
print('Online Status:', sammy['online'])
print('Follower Count:', sammy['followers'])

# Outputs

Sammy dict: {'username': 'sammy', 'online': True, 'followers': 42}
Username: sammy
Online Status: True
Follower Count: 42
```

## Dictionary Properties
  * Each item in a dictionary is a key, value pair.
## Keys
  * The unique address for a dictionary value's location
### Key Properties:
  * Must be **immutable** (strings, numbers, tuples, frozenset(?)) 
  * **UNIQUE** meaning two key values cannot exist within the single dictionary
    * NEWEST CREATED ITEM with a duplicate KEY supercedes the previous declaration
    * Supercede: Takes the place, or position of

## Values
  * Values of a dictionary within a key can be any data type.

## Updating a Dictionary
  * We can modify existing values by referencing the key.
  * We can also add nwe values by creating a new key.
  * We can overwrite a value at an existing key by referencing and recreating the value for it
```python
# Update Example

sammy = {
    'username': 'sammy',
    'online': True,
    'followers': 42
}

sammy['followers'] += 10 # We are adding 10 to the value located at key: 'followers'
sammy['verified'] = True # We added a new value at a new key: 'verified'
sammy['username'] = 'SammySammy'

print('Sammy Dict:', sammy)

# Outputs 
Sammy Dict: {'username': 'SammySammy', 'online': True, 'followers': 52, 'verified': True}
```
## Deletion with Dictionary
  * We can delete a key, which also gets rid of the value connected to the key
  * We can empty out the entire dictionary
  * We can delete the dictionary (uncommon usage) 
 ```python
 # Deletion Example

sammy = {
    'username': 'sammy',
    'online': True,
    'followers': 42
}

del sammy['followers'] # del is a keyword used to help us to execute a removal
print('followers key deleted:', sammy)

sammy.clear() # {} is considered an empty dict
print('emptying out a dictionary', sammy)
print('--\n\n')

# Output
followers key deleted: {'username': 'sammy', 'online': True}
emptying out a dictionary {}

del sammy
print('Deleting sammy, should create an error when referenced again', sammy)

---------------------------------------------------------------------------

NameError                                 Traceback (most recent call last)

<ipython-input-11-d3cbe81f2de2> in <module>
     15
     16 del sammy
---> 17 print('Deleting sammy, should create an error when referenced again', sammy)


NameError: name 'sammy' is not defined
```
## Other uses with Dictionaries
  * Membership
  * Built-in Functions
#  
   Just refer to [note](https://mrparkonline.github.io/courses/datastruct/dictionary/)   
   
## Duplicate a Dictionary and Copy Keys Only 
```python
# Duplicate a Dictionary

sammy = {
    'username': 'sammy',
    'online': True,
    'followers': 42
}

sammy_copy1 = sammy.copy()
sammy_copy2 = sammy

sammy['verified'] = True

print('sammy_copy1:', sammy_copy1)
print('sammy_copy2:', sammy_copy2)
print('--')

# Duplicate keys only

tammy = tammy.fromkeys(sammy) # Notice that all key's values are None ... aka empty

print('tammy dict:', tammy)

# Outputs 
sammy_copy1: {'username': 'sammy', 'online': True, 'followers': 42}
sammy_copy2: {'username': 'sammy', 'online': True, 'followers': 42, 'verified': True}
--
tammy dict: {'username': None, 'online': None, 'followers': None, 'verified': None}
``` 

## Dicitionary Methods
### THESE ARE A SET OF METHODS 
#### Let A and B be a dictionary
  * ```A.keys()``` –> Returns a sequence of keys/addresses in A
  * ```A.values()``` –> Returns a sequence of item values in A
  * ```A.items()``` –> Returns a sequence of key,item pairs in A
  * ```A.get(address)``` –> Returns the item value at address
  * ```A.update(B)``` –> Extends A with the dictionary of key,value pairs of B
#
  Yeah im not copying the code over... refer to [note](https://mrparkonline.github.io/courses/datastruct/dictionary/)  
  
## Iterating a Dictionary
  * Three key methods to take advantage of:
    1. Iterating the keys
    2. Iterating the values
    3. Iterating the key, value pairs by unpacking.
#
  Refer to [note](https://mrparkonline.github.io/courses/datastruct/dictionary/) again :)

## dict() Constructor Dictionary Comprehension
  * We can turn other data types into dictionaries
  * Also similar to lists, tuples, and sets, dictionaries also support comprehension

### Note:
  * You gotta specify where the keys are where the values are. 
```python
# dict() Example

example_data = [
    ('one', 3),
    ('two', 3),
    ('three', 5)
]

data_dict = dict(example_data)
print('data_dict:', data_dict)
print('--')

# Dictionary Comprehension
# Goal: Take string numerals and assign them with their integer square
# - keys : string numerals
# - values: integer squares

example_data2 = ['1', '2', '3', '4', '5']

data2_dict = {x : int(x)**2 for x in example_data2}

print('data2_dict:', data2_dict)

# Output 
data_dict: {'one': 3, 'two': 3, 'three': 5}
--
data2_dict: {'1': 1, '2': 4, '3': 9, '4': 16, '5': 25}
```
