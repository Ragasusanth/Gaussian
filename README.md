# Gaussian Elimination

## AIM:
To write a program to find the solution of a matrix using Gaussian Elimination.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Moodle-Code Runner

## Algorithm

### Step 1: Start the Program.

### Step 2: Import required libraries:

numpy for array handling.

sys to exit the program in case of divide-by-zero.

### Step 3: Input the Size and Augmented Matrix
Read the number of unknowns n.

Create an augmented matrix a of size n × (n+1) and a solution vector X of size n.

Take user input to fill the augmented matrix a.

### Step 4:  Forward Elimination 

For each pivot row i, check for divide-by-zero.

For all rows below i, compute the ratio a[j][i]/a[i][i] and eliminate the coefficient below the pivot.

### Step 5: Solve the last variable directly.

### Step 6: Solve remaining variables using previously computed values.

### Step 7: Print the values of all unknowns.

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

