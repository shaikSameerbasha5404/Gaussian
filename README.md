# Gaussian Elimination

## AIM:
To write a program to find the solution of a matrix using Gaussian Elimination.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Moodle-Code Runner

## Algorithm
1. Declare the variable and read the order of matrix n
2. Take the coefficients of linear equations as: DO for k=1 to n....
3. Do for i=k+1 to n,do for j=k+1 to n+1....
4. Compute X[n]=a[n][n+1]/a[n][n] 
5. Do for k=n-1 to 1,sum=0
6. Display the result.
## Program:
```python
'''Program to solve a matrix using Gaussian elimination with partial pivoting.
Developed by: shaik sameer basha
RegisterNumber: 22004926
'''
import numpy as np
import sys
n=int(input())
a=np.zeros((n,n+1))
X=np.zeros(n)
for i in range(n):
    for j in range(n+1):
        a[i][j]=float(input())
        
for i in range(n):
    if a[i][j]==0.0:
        sys.exist('Divide by zero found')
        
    for j in range(i+1,n):
        ratio=a[j][i]/a[i][i]
        
        for k in range(n+1):
            a[j][k]=a[j][k]-ratio*a[i][k]
        
X[n-1]=a[n-1][n]/a[n-1][n-1]

for i in range(n-2,-1,-1):
    X[i]=a[i][n]
    
    for j in range(i+1,n):
        X[i]=X[i]-a[i][j]*X[j]
        
    X[i]=X[i]/a[i][i]
    
for i in range(n):
    print('X%d = %0.2f'%(i,X[i]),end=' ')
```
## Output:
![g elmination_output](https://user-images.githubusercontent.com/118707756/213451285-084a3762-d216-4712-b851-606c1af58bcf.png)

## Result:
Thus the program to find the solution of a matrix using Gaussian Elimination is written and verified using python programming.

