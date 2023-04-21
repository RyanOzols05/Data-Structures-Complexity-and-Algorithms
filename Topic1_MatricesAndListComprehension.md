# Matrices in Python 3
------
**What is a Matrix?**
------
* A matrix is a representation in a 2-Dimenstional Array of numbers, symbols, or expressions
* In CS, especially Python, we can utilize a list within a list to begin creating data structures that have values in rows and columns, like a table would
* There are external modules and libraries that can be imported to assist with the process, however it is still possible without importing anything
------
**Mathematical Matrix Diagram**
------
! [alt text](https://mrparkonline.github.io/figures/matrix_fig01.png "Mathematical Matrix Diagram"
* Above is a mathematical notation that provides a visual representation of a matrix
* The explanation for the matrix is as follows:
  * Let A represent the matrix
  * Matrix A has n rows and m columns(in this case, n = 2 and m = 4)
  * Row 1 has values of 1 2 3 4
  * Column 2 has values of 2 6
------
**Matrix A in Python 3**
------
* The following is a python representation of the above matrix
```python
matrix_A = [
    [1, 2, 3, 4],
    [5, 6, 7, 8]
]
# Accessing matrix_A
print('Row 1: %s' % matrix_A[0])
print('Value at Row 2 Column 2: %s' % matrix_A[1][1])
# The outputs would be as follows:
# Row 1: [1, 2, 3, 4]
# Value at Row 2 Column 2: 6
```
* There is no data structure called a "Matrix" in python, which is what requires us to code a list within a list
* When doing so, the following rules must be followed:
  * All rows and all columns must contain the same amount of values
  * All items in the 2D list must be of the same data type
  * Due to indexing starting at 0, row 1 is located at matrix_A[0]
------
# List Comprehension in Python 3
------
**What is List Comprehension?**
------

------
**List Comprehension Example 1**
------

------
**How Does List Comprehension Work?**
------

------
**List Comprehension Example 2**
------

------
**List Comprehension Example 3**
------

------
