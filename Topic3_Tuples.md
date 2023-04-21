# Tuples Notes
------
**What are Tuples?**
------
* String and Lists are two iterable data types that are similar to each other while having a few important differences:
    * Strings only allow alphanumeric characters/symbols to represent text
    * Lists allow all data types as the members/items of a list
    * Strings are immutable while Lists are mutable
* These differences can become an annoyance when the following data structure is required:
    * It must be immutable
    * It must allow for items of different data types
    * It must be iterable
    * It must be nestable
* Tuple is the data structure that can be used to solve all of these
------
**How to use Tuples**
------
* Tuples are declared using a set of parenthesis, aka ()
* () is an empty tuple
* (50,) is a singleton tuple
    * The comma is required
* Tuples are slicable, meaning they're indexable when using square brackets
------
**Tuple Example 1**
------
```python
tup = ('C', ' Java', 'Python')
empty_tup = ()
single_tup = ('Park',)
print(tup) # Output: '('C', ' Java', 'Python')'
print(empty_tup) # Output: '()'
print(single_tup) # Output: '('Park',)'
```
------
**Tuple Operators**
------
* Concatenation(```concat_```): Joins two tuples
* Repetition(```repet_```): Repeats a list multiple times
* Membership: Utilizes 'in' and 'not in' operators to check if a value exists in a tuple
```python
# Concatenation
a = (1,2,3)
b = (4,5,6)
concat_result = a + b
print('a+b:', concat_result)
# Repetition
c = ('Hi!',)
repet_result = c * 3
print('c*3', repet_result)
# Membership
d = a + b + c
print('d:', d)
print('\'Hi!\' in d:', 'Hi!' in d)
print('7 in d:', 7 in d)
'''
Output:
a+b: (1, 2, 3, 4, 5, 6)
c*3 ('Hi!', 'Hi!', 'Hi!')
d: (1, 2, 3, 4, 5, 6, 'Hi!')
'Hi!' in d: True
7 in d: False
'''
```
------
**Indexing, Iterating, and Slicing Tuples**
------
```python
# Iterating
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
'''
Output:
Tuple example items:
C
Java
Python
C#
JavaScript
--
Index 1: Java
Last Value: JavaScript
Backwards: ('JavaScript', 'C#', 'Python', 'Java', 'C')
Every other: ('C', 'Python', 'JavaScript')
From 1 to end: ('Java', 'Python', 'C#', 'JavaScript')
From 1 to 3: ('Java', 'Python')
'''
```
------
**Built-in Functions with Tuples**
------
```python
example = ('C', 'Java', 'Python', 'C#', 'JavaScript')
print('Length:', len(example))
print('Minimum value:', min(example))
print('Maximum value:', max(example))
print('--')
word = 'Hello'
array = [1,2,3,4]
array_array = [[1],[2,3],[4]]
print('String to Tuple:', tuple(word))
print('List to Tuple:', tuple(array))
print('2D array to Tuple:', tuple(array_array))
print('--')
array_array[0][0] = 'p'
print(array_array)
# Note: There are no mutable data types in this tuple
'''
Output:
Length: 5
Minimum value: C
Maximum value: Python
--
String to Tuple: ('H', 'e', 'l', 'l', 'o')
List to Tuple: (1, 2, 3, 4)
2D array to Tuple: ([1], [2, 3], [4])
--
[['p'], [2, 3], [4]]
'''
```
------
**Tuple Comprehension**
------
```python
even_tup = tuple(i for i in range(1,101) if i % 2 == 0)
print(even_tup)
# This outputs every number from 1 to 100
```
* The parenthesis were taken for a different function in python, which is why comprehension like this must be done
* Tuple Comprehension has the same general format as List Comprehension does
------
**Packing and Unpacking Tuples**
------
```python
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
'''
Output:
Packed prime values: (2, 3, 5)
fib_0: 0
fib_1: 1
fib_n: (1, 2, 3, 5, 8)
'''
```
*Explanation*
* Packing collects the values of multiple variables and assigns them to a single variable
* Unpacking allows us to assign specific values from a tuple to different variables
* This is very useful when combined with variable arguments for Function Definition & Function Calls
------
