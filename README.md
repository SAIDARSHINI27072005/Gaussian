# Gaussian Elimination

## AIM:
To write a program to find the solution of a matrix using Gaussian Elimination.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Moodle-Code Runner

## Algorithm
1. The code takes the size of a square matrix (number of rows/columns) and the numbers for the matrix and constants in the linear equations.

2. It checks if any number in a special position in the matrix is zero.

3. It changes the matrix so that it becomes a special kind where most numbers below the main diagonal are zeros.

4. It starts from the bottom and works upwards, finding the values for each variable by using the values it already found.

## Program:
```
'''Program to solve a matrix using Gaussian elimination without partial pivoting.
Developed by: SAI DARSHINI R S
RegisterNumber: 23007938
'''
import numpy as np
import sys
n=int(input())
a=np.zeros((n,n+1))
x=np.zeros(n)
for i in range(n):
    for j in range(n+1):
        a[i][j]=float(input())
for i in range(n):
    if a[i][j]==0.0:
        sys.exit('Divide by zero detected!')
    for j in range(i+1,n):
        ratio=a[j][i]/a[i][i]
        for k in range(n+1):
            a[j][k]=a[j][k]-ratio*a[i][k]
x[n-1]=a[n-1][n]/a[n-1][n-1]
for i in range(n-2,-1,-1):
    x[i]=a[i][n]
    for j in range(i+1,n):
        x[i]=x[i]-a[i][j]*x[j]
    x[i]=x[i]/a[i][i]
for i in range(n):
    print('X%d = %0.2f'%(i,x[i]),end=" ")
```

## Output:

![Alt text](image.png)

## Result:
Thus the program to find the solution of a matrix using Gaussian Elimination is written and verified using python programming.

