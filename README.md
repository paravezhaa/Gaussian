# Gaussian Elimination

## AIM:
To write a program to find the solution of a matrix using Gaussian Elimination.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Moodle-Code Runner

## Algorithm
1.Input matrix dimensions and initialize augmented matrix and solution vector.

2.Populate the augmented matrix with user inputs.

3.Perform Gaussian elimination to reduce the matrix to upper 
triangular form, ensuring no division by zero.

4.Back substitute to compute solution values for the variables.

5.Print the solution vector formatted to two decimal places.

## Program:
```
Program to find the solution of a matrix using Gaussian Elimination.
Developed by: Paravezhaa M
Register Number: 212225220070
```
```python
import os
os.environ["OPENBLAS_NUM_THREADS"] = "1"

n = int(input())

a = []
for i in range(n):
    row = []
    for j in range(n + 1):
        row.append(float(input()))
    a.append(row)

for i in range(n):
    for j in range(i + 1, n):
        factor = a[j][i] / a[i][i]
        for k in range(i, n + 1):
            a[j][k] -= factor * a[i][k]

x = [0] * n
for i in range(n - 1, -1, -1):
    x[i] = a[i][n]
    for j in range(i + 1, n):
        x[i] -= a[i][j] * x[j]
    x[i] /= a[i][i]

for i in range(n):
    print(f"X{i} = {x[i]:.2f}", end=" ")
```


## Output:
![gaussian elimination]()
<img width="766" height="506" alt="image" src="https://github.com/user-attachments/assets/0f922082-9aca-43a2-a726-7559bc74406f" />


## Result:
Thus the program to find the solution of a matrix using Gaussian Elimination is written and verified using python programming.

