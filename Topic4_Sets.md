# Sets
------
**What are Sets?**
------
* Sets are unordered collections of data containing no duplicates
* Set is the mathematical term for describing a collection of unique objects
* By following the characteristics and operations of a mathematical set, we can utilize a set in python
------
**Using Sets in Python**
------
*How to Define a Set*
```python
example_set1 = {1, 2, 3}
example_set2 = {'h','e','l','l','o'}
print('example_set1:', example_set1)
print('example_set2:', example_set2)
print('--')

singleton_set = {7}
empty_set = set()
print('Singleton:', singleton_set)
print('Empty Set:', empty_set)
'''
Output:
example_set1: {1, 2, 3}
example_set2: {'o', 'e', 'h', 'l'}
--
Singleton: {7}
Empty Set: set()
```
*Basic Built-in Functions w/ Sets*
```python
example_set = set('hello') # set() turns an iterable into a set
print('example_set:', example_set)
print('--')

print('Number of Values:', len(example_set))
print('Minimum Value:', min(example_set))
print('Maximum Value:', max(example_set))
print('--')

# tuple to set
tup = (2,3,5,7)
print('tup to set:', set(tup))

# list to set
array = ['orange']*2 +  ['watermelon', 'apple'] + ['kiwi'] * 10
print('Original Array:', array)
print('list to set:', set(array))
'''
Output:
example_set: {'o', 'e', 'h', 'l'}
--
Number of Values: 4
Minimum Value: e
Maximum Value: o
--
tup to set: {2, 3, 5, 7}
Original Array: ['orange', 'orange', 'watermelon', 'apple', 'kiwi', 'kiwi', 'kiwi', 'kiwi', 'kiwi', 'kiwi', 'kiwi', 'kiwi', 'kiwi', 'kiwi']
list to set: {'watermelon', 'orange', 'apple', 'kiwi'}
'''
```
*Basic Membership Operators*
* Membership is one of the key operations with set because:
    * Sets have no duplicates
    * The membership operation for set is one of the fastest compared to strings, lists, and tuples
    * Using the membership operation allows for certainty about if a target exists or doesn't exist in the data
```python
example_set = set('hello')
print("Membership of: \'h\'", 'h' in example_set)
print("Non-Membership of: \'z\'", 'z' not in example_set)
'''
Output:
Membership of: 'h' True
Non-Membership of: 'z' True
'''
```
*Accessing Values in a Set*
* Due to sets being unordered, there's no concept of indexing or slicing a set, though sets are iterable
```python
example_set = {2,3,5,7,11,13}
for v in example_set:
  print('Values of example_set:', v)
'''
Output:
Values of example_set: 2
Values of example_set: 3
Values of example_set: 5
Values of example_set: 7
Values of example_set: 11
Values of example_set: 13
'''
```
*Adding/Removing Values*
* Since sets are mutable, it's possible to add or remove values from a set
* There are methods that are used for lists that can be used on sets
```python
languages = set()
programming_languages = ['C', 'C#', 'Java', 'Python', 'HTML', 'CSS', 'JavaScript', 'Haskell']
for item in programming_languages:
  languages.add(item)
print('Languages set:', languages)
print('--')
languages.discard('HTML')
print('HTML deleted:', languages)
languages.remove('CSS')
print('CSS deleted:', languages)
random_remove = languages.pop()
print('Randomly Removed value:', random_remove)
languages.clear()
print('Empty languages:', languages)
'''
Output:
Languages set: {'HTML', 'CSS', 'JavaScript', 'Python', 'Haskell', 'Java', 'C', 'C#'}
--
HTML deleted: {'CSS', 'JavaScript', 'Python', 'Haskell', 'Java', 'C', 'C#'}
CSS deleted: {'JavaScript', 'Python', 'Haskell', 'Java', 'C', 'C#'}
Randomly Removed value: JavaScript
Empty languages: set()
'''
```
------
**Powering Up Sets: Set Operators**
------
* Much like the mathematical version, sets can utilize many operators to help complete more complex calculation
* Most of the operators have a method counterpart due to sets being mutable
* Each of these operators will be demonstrated below, though strings will be used instead of sets to make demonstration easier
*Union*
* The joining/combining of two sets
```python
# Union Example:
set1 = set('hello')
set2 = set('world')
result = set1 | set2 # | is the union operator
print('set1 union set 2:', result)
'''
Output:
set1 union set 2: {'h', 'w', 'e', 'r', 'l', 'd', 'o'}
'''
```
*Intersection*
* Members/Items that exist in both sets
```python
set1 = set('hello')
set2 = set('world')
result = set1 & set2 # & is the intersection operator
print('Intersection of set1 and set2:', result)
'''
Output:
Intersection of set1 and set2: {'o', 'l'}
'''
```
*Difference*
* Members/Items that only exist in the first set
```python
set1 = set('hello')
set2 = set('world')
result1 = set1 - set2 # - is the difference operator
result2 = set2 - set1
print('set1 - set2:', result1)
print('set2 - set1:', result2)
'''
Output:
set1 - set2: {'e', 'h'}
set2 - set1: {'w', 'd', 'r'}
'''
```
*Symmetric Difference*
* Members/Items that only exist in one set but noth both sets
```python
set1 = set('hello')
set2 = set('world')
result = set1 ^ set2 # ^ is the symmetric difference operator
print('Symmetric Difference of:', result)
'''
Output:
Symmetric Difference of: {'e', 'h', 'w', 'd', 'r'}
'''
```
*Proper Subset*
* This is a boolean operator
    * A is a proper subset of B if all of A can be found in B while not being exactly the same
```python
set1 = {1,2,3}
set2 = {1,2,3,4}
set3 = {1,2,3}
set4 = set('hello')
print('Is set1 proper subset of set2?:', set1 < set2) # < is the proper subset operator
print('Is set1 proper subset of set3?:', set1 < set3)
print('Is set1 proper subset of set4?:', set1 < set4)
'''
Output:
Is set1 proper subset of set2?: True
Is set1 proper subset of set3?: False
Is set1 proper subset of set4?: False
'''
```
*Subset*
* This is a boolean operator
    * A is a subset of B if A < B is true, but A can equal B unlike a proper subset
```python
set1 = {1,2,3}
set2 = {1,2,3,4}
set3 = {1,2,3}
set4 = set('hello')
print('Is set1 a subset of set2?:', set1 <= set2) # <= is the subset operator
print('Is set1 a subset of set3?:', set1 <= set3)
print('Is set1 a subset of set4?:', set1 <= set4)
'''
Output:
Is set1 a subset of set2?: True
Is set1 a subset of set3?: True
Is set1 a subset of set4?: False
'''
```
*Proper Superset*
* This is a boolean operator
    * A is a proper superset of B if A contains all values of B and more unique values, but A and B can't equal each other
```python
set1 = {1,2,3,4}
set2 = {1,2,3,4}
set3 = {1,2,3}
set4 = set('hello')
print('Is set1 proper superset of set2?:', set1 > set2) # > is the proper superset operator
print('Is set1 proper superset of set3?:', set1 > set3)
print('Is set1 proper superset of set4?:', set1 > set4)
'''
Output:
Is set1 proper superset of set2?: False
Is set1 proper superset of set3?: True
Is set1 proper superset of set4?: False
'''
```
*Superset*
* This is a boolean operator
    * A is a superset of B if A > B or A == B
```python
set1 = {1,2,3,4}
set2 = {1,2,3,4}
set3 = {1,2,3}
set4 = set('hello')
print('Is set1 superset of set2?:', set1 >= set2) # >= is the proper superset operator
print('Is set1 superset of set3?:', set1 >= set3)
print('Is set1 superset of set4?:', set1 >= set4)
'''
Output:
Is set1 superset of set2?: True
Is set1 superset of set3?: True
Is set1 superset of set4?: False
'''
```
------
**Disjoint: A Set Behaviour Property**
------
* Two sets are considered disjointed when they share no values
* With A and B representing different sets:
    * If A & B are empty, set A & B is considered disjointed
    * This can be checked using a method called ```isdisjoint()```
* '&' is the intersection operator
```python
set1 = {1,2,3,4}
set2 = {5,6,7}
set3 = {1,2,3,4,5}
print('set1 intersect set2:', set1 & set2)
print('set1 intersect set3:', set1 & set3)
print('--')
print('set 1 disjoint set 2 check:', set1.isdisjoint(set2))
print('set 1 disjoint set 3 check:', set2.isdisjoint(set3))
'''
Output:
set1 intersect set2: set()
set1 intersect set3: {1, 2, 3, 4}
--
set 1 disjoint set 2 check: True
set 1 disjoint set 3 check: False
'''
```
------
**Set Operators as Methods**
------
```python
# Union
a = set('abracadabra')
b = set('alacazam')
a.union(b)
print('Union:', a)

# Intersection
a = set('abracadabra')
b = set('alacazam')
a.intersection(b)
print('Intersection:', a)

# Difference
a = set('abracadabra')
b = set('alacazam')
a.difference(b)
print('Difference:', a)

# Symmeteric Difference
a = set('abracadabra')
b = set('alacazam')
a.symmetric_difference(b)
print('Symmetric Difference:', a)

# Subset
a = set('abracadabra')
b = set('alacazam')
print('Subset:', a.issubset(b))

# Superset
a = set('abracadabra')
b = set('alacazam')
print('Superset:', a.issuperset(b))
print('--')

# There are no proper subset/superset methods

# copy
a = set('abracadabra')
b = a.copy()
c = a
a.add('z')
print('.copy() examples:')
print('set a:', a)
print('set b:', b)
print('set c:', c)
'''
Output:
Union: {'b', 'a', 'r', 'd', 'c'}
Intersection: {'b', 'a', 'r', 'd', 'c'}
Difference: {'b', 'a', 'r', 'd', 'c'}
Symmetric Difference: {'b', 'a', 'r', 'd', 'c'}
Subset: False
Superset: False
--
.copy() examples:
set a: {'b', 'a', 'z', 'r', 'd', 'c'}
set b: {'b', 'a', 'd', 'r', 'c'}
set c: {'b', 'a', 'z', 'r', 'd', 'c'}
'''
```
*Assignment Operation and Updating Methods*
* This is a way to affect an original set with another set while applying the result back to the original set
```python
# Union and Update --> Update the set, adding items from all other sets
a = set('abracadabra')
b = set('alacazam')
a |= b # same as: a.update(b)
print('Union Update:', a)

# Intersection and Update --> Update the set, only keeping items found in all sets
a = set('abracadabra')
b = set('alacazam')
a &= b # same as: a.intersection_update(b)
print('Intersection Update:', a)

# Difference and Update --> Update the set, removing items found in other sets
a = set('abracadabra')
b = set('alacazam')
a -= b # same as: a.difference_update(b)
print('Difference Update:', a)

# Symmetric Difference and Update --> Update the set, only keeping items found in one set but not both
a = set('abracadabra')
b = set('alacazam')
a ^= b # same as: a.symmetric_difference_update(b)
print('Symmeteric Difference Update:', a)
'''
Output:
Union Update: {'b', 'a', 'z', 'r', 'l', 'm', 'd', 'c'}
Intersection Update: {'c', 'a'}
Difference Update: {'b', 'r', 'd'}
Symmeteric Difference Update: {'b', 'z', 'r', 'l', 'm', 'd'}
'''
```
------
**Set Comprehension**
------
* Sets also support comprehension
```python
def isPalindrome(x):
  return x == x[::-1]
nums = list(range(1,10000))
palindromic_set = {num for num in nums if isPalindrome(str(num))}
print('Palindromic Numbers Set from 1 to 10000:')
print(palindromic_set)
'''
Output:
This will output every number that's a palindrome from 1 to 10000
'''
```
------
**Final Notes**
------
* Sets aren't sliceable or indexable
* Sets cannot contain other sets
* Sets don't have an order or order of insertion, meaning they can't guarantee their values are in order
* Sets don't record a value's position
------
