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

```
import os
os.environ["OPENBLAS_NUM_THREADS"]="1"

n = int(input())


A = []
for i in range(n):
    row = []
    for j in range(n + 1):
        row.append(float(input()))
    A.append(row)


for i in range(n):
    for j in range(i + 1, n):
        ratio = A[j][i] / A[i][i]
        for k in range(n + 1):
            A[j][k] = A[j][k] - ratio * A[i][k]


X = [0 for _ in range(n)]

for i in range(n - 1, -1, -1):
    X[i] = A[i][n]
    for j in range(i + 1, n):
        X[i] -= A[i][j] * X[j]
    X[i] = X[i] / A[i][i]


for i in range(n):
    print(f"X{i} = {X[i]:.2f}", end=" ")
```
## Output:
<img width="1229" height="588" alt="image" src="https://github.com/user-attachments/assets/b97b836c-185c-488f-8a80-63a0d96afd34" />


## Result:
Thus the program to find the solution of a matrix using Gaussian Elimination is written and verified using python programming.

