# Gaussian Elimination

## AIM:
To write a program to find the solution of a matrix using Gaussian Elimination.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Moodle-Code Runner

## Algorithm

### Step 1: Input the number of variables and initialize the augmented matrix.

### Step 2: Fill in the augmented matrix with user inputs.

### Step 3: Check for zero pivot elements to avoid division by zero.

### Step 4: Apply forward elimination to convert the matrix to upper triangular form.

### Step 5: Perform back substitution to solve for the variables.

### Step 6: Display the values of the solution vector X.

## Program:
```
'''Program to solve a matrix using Gaussian elimination without partial pivoting.
Developed by: RAGA SUSANTH  
RegisterNumber: 212224230217
'''
import numpy as np
import sys
n=int(input())
a=np.zeros((n,n+1))
X=np.zeros(n)
for i in range (n):
    for j in range(n+1):
        a[i][j]=float(input())
        
for i in range(n):
    if a[i][i]==0.0:
        sys.exit('Divide by zero detected!')
        
    for j in range(i+1,n):
        ratio=a[j][i]/a[i][i]
        
        for k in range(n+1):
            a[j][k]=a[j][k]-ratio*a[i][k]
            
X[n-1]=a[n-1][n]/a[n-1][n-1]

for i in range (n-1,-1,-1):
    X[i]=a[i][n]
    
    for j in range (i+1,n):
        X[i]=X[i]-a[i][j]*X[j]
        
    X[i]=X[i]/a[i][i]
for i in range (n):
    print('X%d = %0.2f ' %(i,X[i]),end='')

```

## Output:

![image](https://github.com/user-attachments/assets/f32fadfb-3256-4ee4-8082-a7dabbdcdc98)


## Result:
Thus the program to find the solution of a matrix using Gaussian Elimination is written and verified using python programming.

