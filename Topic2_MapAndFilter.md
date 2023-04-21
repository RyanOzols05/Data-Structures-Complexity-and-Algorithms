# Map & Filter In Python 3
------
**The Map Function**
------

------
**Example 1**
------
```python

```
------
**Example 2**
------
```python

```
------
**The Filter Function**
------

------
**Example 3**
------
```python

```
------
**Palindrome Example**
------
The program below will output a list of palindromic numbers from 1 to 1000
```python
def isPalindrome(x):
  return x == x[::-1]
array = list(range(1,10000))
palindromic_numbers = list(map(int, filter(isPalindrome, map(str, array))))
print('Palindromic Numbers from 1 to 10,000', palindromicNumbers)
```
Code explanation:
* 
------
