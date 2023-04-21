# Map & Filter In Python 3
------
**The Map Function**
------
* The purpose of the map function is to apply functions to iterable data
* The map function is formatted as so: map(function_name, sequence)
    * function_name = any function that returns a chosen value
    * sequence = any iterable data type
------
**Example 1**
------
Squaring given numbers
```python
def square(num):
  return num ** 2
array = list(range(1,11))
square_array = list(map(square, array))
print('Original Array:', array)
print('Array Squared:', square_array)
# Original Array: [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
# Array Squared: [1, 4, 9, 16, 25, 36, 49, 64, 81, 100]
```
Since the map function doesn't return any specific data type, we execute a list function after applying the map function

------
**Example 2**
------
Capitalizing the inputted word/phrase
```python
def upper(x):
  return x.upper()
word = 'hello world!'
upper_word = ''.join(list(map(upper, word)))
print(word) # Output: hello world!
print(upper_word) # Output: HELLO WORLD!

# simpler way:
print(word.upper()) # Output: HELLO WORLD!
```
This is meant as an example as to how map() isn't necessary every time a change is to be made to a string

------
**The Filter Function**
------
* The filter function is used to filter data out of a data set only if it satisfies a certain condition
* The filter function is formatted as so: filter(bool_returning_function, sequence)
    * function = must be a function that can handle the items inside the sequence as it's arguments and must be able to return a boolean value
    * sequence = any iterable data type
------
**Example 3**
------
Prints all odd numbers from 1 to 100
```python
def isOdd(x):
  return x % 2 != 0
array = list(range(1,101))
odds = list(filter(isOdd, array))
print('Odd Numbers from 1 to 100:', odds)
```
This code is meant as a simple way to show how filter can be used to filter out variables if a condition is satisfied

------
**Palindrome Example**
------
The program below will output a list of palindromic numbers from 1 to 10000
```python
def isPalindrome(x):
  return x == x[::-1]
array = list(range(1,10000))
palindromic_numbers = list(map(int, filter(isPalindrome, map(str, array))))
print('Palindromic Numbers from 1 to 10,000', palindromicNumbers)
```
Code explanation:
1. String version of array --> map(str, array)
2. Filter out the palindrome --> filter(isPalindrome, map(str, array))
3. Remap all the values back to integers --> map(int, palindrome)
4. Turn the mapped integers iterable back inside of a list --> list(palindromicNumbers)

How the code would look with multiple defined variables:
* array = list(range(1,10000))
* str_array = map(str, array)
* palindromes = filter(isPalindrome, str_array)
* palindromics = map(int, palindromes)
* palindromic_numbers = list(palindromes)
------
