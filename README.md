# Gaussian Elimination

## AIM:
To write a program to find the solution of a matrix using Gaussian Elimination.

## Equipments Required:
2. Anaconda – Python 3.7 Installation / Moodle-Code Runner

## Algorithm
1.Input the number of equations n.
2.Initialize an augmented matrix a of size n x (n+1) filled with zeros.
➤ This matrix holds the coefficients and constants.
3.Initialize a solution array x of size n filled with zeros.
4.Loop through rows (i = 0 to n-1):
→ For each row, loop through columns (j = 0 to n):
→ Input the value and assign to a[i][j].
➤ This fills the augmented matrix with coefficients and constants.
5.Begin Gaussian Elimination (Forward Elimination):
6.If a[i][i] == 0, exit with "Divide by zero detected".
    For rows below (j = i+1 to n-1):
    Compute ratio = a[j][i] / a[i][i].
    Update row: a[j][k] -= ratio * a[i][k] for all k.
7.Initialize last value of x (solution array):
x[n-1] = a[n-1][n] / a[n-1][n-1]
➤ This starts the Back Substitution.
8.Back Substitution (i = n–1 to 0):
    Set x[i] = a[i][n]
    For j = i+1 to n–1: subtract a[i][j] * x[j] from x[i]
    Final step: x[i] /= a[i][i]
9.Print the final solutions x[0], x[1], ..., x[n-1] in formatted form.
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
```

## Output:
![image](https://github.com/user-attachments/assets/4ece68c9-61ea-4793-bce2-f9b3737000d6)
## Result:
Thus the program to find the solution of a matrix using Gaussian Elimination is written and verified using python programming.

