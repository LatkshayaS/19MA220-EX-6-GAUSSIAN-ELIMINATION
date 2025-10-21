#E-X6- Gaussian Elimination

## AIM:
To write a program to find the solution of a matrix using Gaussian Elimination.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Moodle-Code Runner

## ALGORITHM:
###Step 1:Import the numpy module and the Decimal library from the decimal module for precise rounding operations.
###Step 2:Get the number of variables (n) from the user.
###Step 3:Create an augmented matrix of size n × (n+1) using np.zeros() to store the coefficients and constants.
###Step 4:Get the elements of the augmented matrix as input from the user.
###Step 5:For each row, check if the diagonal element is zero. 
If zero, terminate the program to avoid division by zero.
###Step 6:Perform the forward elimination process to convert the matrix into an upper triangular form.
###Step 7:
Use back subst
## Program:
```
/*
Program to find the solution of a matrix using Gaussian Elimination.
Developed by: 
RegisterNumber: 
*/
'''Program to solve a matrix using Gaussian elimination without partial pivoting.
Developed by: Latkshaya S
RegisterNumber: 25009540
'''
import numpy as np
from decimal import Decimal,ROUND_HALF_UP

n=int(input())
a=np.zeros((n,n+1))
x=np.zeros(n)
for i in range(n):
    for j in range(n+1):
        a[i][j]=float(input())
for i in range (n):
        if a[i][i]==0.0:
            sys.exit("Divide by zero detected")
        for j in range (i+1,n):
            ratio=a[j][i]/a[i][i]
            for k in range (n+1):
                a[j][k]=a[j][k]-ratio*a[i][k]
x[n-1]=a[n-1][n]/a[n-1][n-1]
for i in range(n-2,-1,-1):
        x[i]=a[i][n]
        for j in range(i+1,n):
            x[i]=x[i]-a[i][j]*x[j]
        x[i]=x[i]/a[i][i] 
for i in range(n):
        print("X%d = %0.2f"%(i,x[i]),end=' ')
            
```

## Output:
![EX5.PNG]()


## Result:
Thus the program to find the solution of a matrix using Gaussian Elimination is written and verified using python programming.

