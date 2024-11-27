

## AIM:
To write a program to find the solution of a matrix using Gaussian Elimination.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Moodle-Code Runner

## Algorithm
1. import numpy
2. assign the values accordingly
3. fix the loop
4. proceed with the print statements
5. End of the program

## Program:
```
import numpy as np
import sys
n=int(input())
a=np.zeros((n,n+1))
x=np.zeros(n)
for i in range(n):
    for j in range(n+1):
        a[i][j]=float(input())
for i in range(n):
    if a[i][i]==0.0:
        sys.exit('Divide by zero detected!')
    for j in range(i+1, n):
        ratio=a[j][i] / a[i][i]
        for k in range(n+1):
            a[j][k] = a[j][k]-ratio *a[i][k]
x[n-1]=a[n-1][n]/a[n-1][n-1]
for i in range(n-2,-1,-1):
    x[i] = a[i][n]
    for j in range(i+1,n):
        x[i]=x[i]-a[i][j]*x[j]
    x[i]=x[i]/a[i][i]
for i in range(n):
    print('X%d = %0.2f'%(i,x[i]),end=' ')


/*
Program to find the solution of a matrix using Gaussian Elimination.
Developed by:D MEAGESWAR 
RegisterNumber:24900815 
*/
```

## Output:
![Screenshot 2024-11-27 185532](https://github.com/user-attachments/assets/58e6e43e-6763-450b-bb26-1e5db5e11dcb)



## Result:
Thus the program to find the solution of a matrix using Gaussian Elimination is written and verified using python programming.

