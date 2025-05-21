# Gaussian Elimination

## AIM:
To write a program to find the solution of a matrix using Gaussian Elimination.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Moodle-Code Runner

## Algorithm
## Step 1:
Start the program and import necessary modules (optional, if using NumPy for input).
## Step 2:
Input the number of equations and variables.
## Step 3:
Create the augmented matrix by taking coefficients of the variables and the constants from each equation.
## Step 4:
Use Gaussian Elimination to convert the augmented matrix into upper triangular form: For each pivot row, eliminate the entries below the pivot by row operations.Swap rows if the pivot element is zero.
## Step 5:
Use back substitution to find the values of the variables starting from the last row upwards.Display the solution for each variable.
## Step 7:
End the program.

## Program:
```python
'''Program to solve a matrix using Gaussian elimination without partial pivoting.
Developed by: Sanjay M
RegisterNumber: 212222110038
'''
import numpy as np
import sys
n = int(input())
a = np.zeros((n,n+1))
x = np.zeros(n)
for i in range(n):
    for j in range(n+1):
        a[i][j] = float(input())
for i in range(n):
    if a[i][i] == 0.0:
        sys.exit('Divide by zero detected!')
    for j in range(i+1,n):
        ratio = a[j][i]/a[i][i]
        for k in range(n+1):
            a[j][k] = a[j][k] - ratio * a[i][k]
x[n-1] = a[n-1][n]/a[n-1][n-1]
for i in range(n-2,-1,-1):
    x[i] = a[i][n]
    for j in range(i+1,n):
        x[i] = x[i] - a[i][j]*x[j]
    x[i] = x[i]/a[i][i]
for i in range(n):
    print('X%d = %0.2f' %(i,x[i]), end=' ')
```

## Output:
![image](https://github.com/user-attachments/assets/543d724f-d0df-46ac-873f-a5c361e5ded8)


## Result:
Thus the program to find the solution of a matrix using Gaussian Elimination is written and verified using python programming.

