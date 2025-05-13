# Gaussian Elimination

## AIM:
To write a program to find the solution of a matrix using Gaussian Elimination.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Moodle-Code Runner

## Algorithm
1. Input the order n and the augmented matrix of size n × (n+1).
2. Perform forward elimination to convert the matrix into upper triangular form.
3. Apply back substitution to find the values of the unknown variables.
4. Print the solution for all variables.

## Program:
```'''Program to solve a matrix using Gaussian elimination without partial pivoting.
Developed by: Abishek P
RegisterNumber : 212224240002
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
    if a[i][j]==0:
        sys.exit('Divide by zero detected')
    for j in range (i+1,n):
        ratio=a[j][i]/a[i][i]
        for k in range(n+1):
            a[j][k]=a[j][k]-ratio *a[i][k]
x[n-1]=a[n-1][n]/a[n-1][n-1]
for i in range(n-1,-1,-1):
    x[i]=a[i][n]
    for j in range(i+1,n):
        x[i]=x[i]-a[i][j]*x[j]
    x[i]=x[i]/a[i][i]
for i in range(n):
    print('X%d = %0.2f'%(i,x[i]),end=' ')
/*
Program to find the solution of a matrix using Gaussian Elimination.
Developed by: 
RegisterNumber: 
*/
```

## Output:
![image](https://github.com/user-attachments/assets/4ece68c9-61ea-4793-bce2-f9b3737000d6)
## Result:
Thus the program to find the solution of a matrix using Gaussian Elimination is written and verified using python programming.

