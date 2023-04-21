# Dictionaries in Python
------
**Common Operations**
------
* A dictionary is a data type that stores a collection of (key, value) pairs in such a way that each possible key will not appear more than once per collection
* Some common operations for dictionaries are:
    * Adding or removing a pair
    * Modifying an existing pair
    * Looking up the value that's associated with a particular key
------
**Defining a Dictionary**
------
* Dictionaries also utilize {} data sets, although their formatting of individual items is different
* Each item in a dictionary must be a key:value pair
```python
# Example
sammy = {
    'username': 'sammy',
    'online': True,
    'followers': 42
}
# Three unique items, each with a unique address and value
print('Sammy dict:', sammy) # Output: 'Sammy dict: {'username': 'sammy', 'online': True, 'followers': 42}'
print('Username:', sammy['username']) # Output: 'Username: sammy'
print('Online Status:', sammy['online']) # Output: 'Online Status: True'
print('Follower Count:', sammy['followers']) # Output: 'Follower Count: 42'
```
------
**Dictionary Properties**
------
Each item in a dictionary is a key:value pair
*Keys*
* Keys are unique addresses for the location of values within a dictionary
* Keys must be immutable(strings, numbers, tuples, frozenset) and unique(two keys can't have the same value)
    * If a new key is created utilizing an already used value, that new key will supercede the previous key
*Values*
* Values within a dictionary can be any data type
*Updating a Dictionary*
* By referencing a key, it's possible to update/modify existing values
* By creating a new key, it's possible to add new values to the dictionary
* It's possible to overwrite a value that exists at a preexisting key by referencing and recreating the value for that key
```python
# Updating Example
sammy = {
    'username': 'sammy',
    'online': True,
    'followers': 42
}
sammy['followers'] += 10
sammy['verified'] = True
sammy['username'] = 'SammySammy'
print('Sammy Dict:', sammy) # Output: 'Sammy Dict: {'username': 'SammySammy', 'online': True, 'followers': 52, 'verified': True}'
```
*Deletion with Dictionary*
* It's possible to delete a key by deleting the value connected to that key
* This makes it possible to empty out or even delete an entire dictionary
```python
# Deletion Example
sammy = {
    'username': 'sammy',
    'online': True,
    'followers': 42
}
del sammy['followers']
print('followers key deleted:', sammy) # Output: 'followers key deleted: {'username': 'sammy', 'online': True}'
sammy.clear()
print('emptying out a dictionary', sammy) # Output: 'emptying out a dictionary {}'
print('--\n\n')
del sammy
print('Deleting sammy, should create an error when referenced again', sammy) # Causes a NameError
```
*Membership*
* The 'in' and 'not in' operators can be used to check if a key is existant inside a dictionary
```python
# Membership Example
sammy = {
    'username': 'sammy',
    'online': True,
    'followers': 42
}
print('Checking for key username:', 'username' in sammy) # Output: 'Checking for key username: True'
print('Checking if followers is not a key:', 'followers' not in sammy) # Output: 'Checking if followers is not a key: False'
```
*Built-In Functions*
```python
# Built-In Function Interactions
sammy = {
    'username': 'sammy',
    'online': True,
    'followers': 42
}
print('Size of sammy dict:', len(sammy)) # Output: 'Size of sammy dict: 3'
print('Largest Key:', max(sammy)) # Output: 'Largest Key: username'
print('Smallest Key:', min(sammy)) # Output: 'Smallest Key: followers'
print('Dict to string:', str(sammy)) # Output: 'Dict to string: {'username': 'sammy', 'online': True, 'followers': 42}'
print('Dict to list:', list(sammy)) # Output: 'Dict to list: ['username', 'online', 'followers']'
```
*Duplicating Dictionaries and Copy Keys Only*
```python
#Duplication Example
sammy = {
    'username': 'sammy',
    'online': True,
    'followers': 42
}
sammy_copy1 = sammy.copy()
sammy_copy2 = sammy
sammy['verified'] = True
print('sammy_copy1:', sammy_copy1) # Output: 'sammy_copy1: {'username': 'sammy', 'online': True, 'followers': 42}'
print('sammy_copy2:', sammy_copy2) # Output: 'sammy_copy2: {'username': 'sammy', 'online': True, 'followers': 42, 'verified': True}'
print('--') # Output: '--'

# Duplicating only keys
tammy = tammy.fromkeys(sammy)
print('tammy dict:', tammy) # Output: 'tammy dict: {'username': None, 'online': None, 'followers': None, 'verified': None}'
```
------
**Dictionary Methods**
------
* Dictionary has it's own built-in methods that can be utilized
* The built-in methods(with A and B both representing dictionaries) are:
    * A.keys() --> Returns a sequence of keys and/or addresses in the dictionary
    * A.values() --> Returns a sequence of item values in the dictionary
    * A.items() --> Returns a sequence of key:value pairs in the dictionary
    * A.get(address) --> Returns the value of the item at the address
    * A.update(B) --> Extends dictionary A with the pairs of dictionary B
```python
# Methods Example
sammy = {
    'username': 'sammy',
    'online': True,
    'followers': 42
}
sammy_hidden = {
    'pwd' : 'qwerty
    'location' : 'Toronto, Ontario'
}
# printing all the keys
print('Sammy Dict Keys:', sammy.keys())
sammy_keys = list(sammy.keys())
print('List of sammy_keys', sammy_keys)
print('--')

# printing all the values
print('Sammy Dict Values:', sammy.values())
print('Sammy Dict Values as a list:', list(sammy.values()))
print('--')

# printing key:value pairs
print('Sammy Dict key, value pairs:', sammy.items())
print('Sammy Dict key, value pairs as a list:', list(sammy.items()))
print('--')

# getting a value
print('Sammy followers value:', sammy.get('followers'))
print('Same as:', sammy['followers'])
print('--')

# updating / extending a dictionary
sammy.update(sammy_hidden)
print('Sammy extended with its hidden values:', sammy)
'''
Output:
Sammy Dict Keys: dict_keys(['username', 'online', 'followers'])
List of sammy_keys ['username', 'online', 'followers']
--
Sammy Dict Values: dict_values(['sammy', True, 42])
Sammy Dict Values as a list: ['sammy', True, 42]
--
Sammy Dict key, value pairs: dict_items([('username', 'sammy'), ('online', True), ('followers', 42)])
Sammy Dict key, value pairs as a list: [('username', 'sammy'), ('online', True), ('followers', 42)]
--
Sammy followers value: 42
Same as: 42
--
Sammy extended with its hidden values: {'username': 'sammy', 'online': True, 'followers': 42, 'pwd': 'qwerty', 'location': 'Toronto, Ontario'}
'''
```
------
**Iterating a Dictionary**
------
* There are three iteration methods that will be taken advantage of:
    * Iterating the keys
    * Iterating the values
    * Iterating the key:value pairs by unpacking
```python
# Iterating Example
sammy = {
    'username': 'sammy',
    'online': True,
    'followers': 42
}

# Example 1: Keys
for k in sammy.keys():
  print('Current key:', k)
print('--\n')

#Example 2: Values
for v in sammy.values():
  print('Current value:', v)
print('--\n')


# Example 3: Key:Value Pair
for k, v in sammy.items():
  print('Current Key:', k)
  print('Current Value:', v)
  print()
'''
Output:
Current key: username
Current key: online
Current key: followers
--

Current value: sammy
Current value: True
Current value: 42
--

Current Key: username
Current Value: sammy

Current Key: online
Current Value: True

Current Key: followers
Current Value: 42
'''
```
------
**dict() Constructor Dictionary Comprehension**
------
* It's possible to turn other data types into dictionaries, and dictionaries also support comprehension
    * *Note: It's important to specify where the keys and values are*
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
example_data2 = ['1', '2', '3', '4', '5']
data2_dict = {x : int(x)**2 for x in example_data2}
print('data2_dict:', data2_dict)
'''
Output:
data_dict: {'one': 3, 'two': 3, 'three': 5}
--
data2_dict: {'1': 1, '2': 4, '3': 9, '4': 16, '5': 25}
'''
```
------
