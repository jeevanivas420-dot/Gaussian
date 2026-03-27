# Gaussian Elimination

## AIM:
To write a program to find the solution of a matrix using Gaussian Elimination.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Moodle-Code Runner

## Algorithm
1. Read the order of matrix and augmented matrix elements from the user.
2. Apply forward elimination to convert the matrix into upper triangular form.
3. Perform back substitution to compute the values of unknowns.
4. Display the solution vector.

## Program:
**Program to find the solution of a matrix using Gaussian Elimination.**
**Developed by: JEEVA NIVAS M**
**RegisterNumber: 21225040148**

```python
import numpy as np
import sys

# Reading number of unknowns
n = int(input())

# Making numpy array of n x n+1 size and initializing 
# to zero for storing augmented matrix
a = np.zeros((n,n+1))

# Making numpy array of n size and initializing 
# to zero for storing solution vector
x = np.zeros(n)

# Reading augmented matrix coefficients
for i in range(n):
    for j in range(n+1):
        a[i][j] = float(input())

# Applying Gauss Elimination
for i in range(n):
    if a[i][i] == 0.0:
        sys.exit('Divide by zero detected!')
        
    for j in range(i+1, n):
        ratio = a[j][i]/a[i][i]
        
        for k in range(n+1):
            a[j][k] = a[j][k] - ratio * a[i][k]

# Back Substitution
x[n-1] = a[n-1][n]/a[n-1][n-1]

for i in range(n-2,-1,-1):
    x[i] = a[i][n]
    
    for j in range(i+1,n):
        x[i] = x[i] - a[i][j]*x[j]
    
    x[i] = x[i]/a[i][i]

# Displaying solution
for i in range(n):
    print('X%d = %0.2f' %(i,x[i]), end = ' ')

```
## Output:
<img width="1229" height="588" alt="image" src="https://github.com/user-attachments/assets/b97b836c-185c-488f-8a80-63a0d96afd34" />


## Result:
Thus the program to find the solution of a matrix using Gaussian Elimination is written and verified using python programming.

