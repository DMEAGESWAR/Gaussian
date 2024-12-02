

## AIM:
To write a program to find the solution of a matrix using Gaussian Elimination.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Moodle-Code Runner

## Algorithm
1. Here's a step-by-step breakdown of the algorithm implemented in the code:

Step 1: Input Matrix Dimensions and Elements

- Read the number of equations (n) from the user.
- Initialize an n x (n+1) matrix a with zeros, where the last column represents the constant terms.
- Initialize an array x of size n to store the solution variables.
- Read the elements of the matrix a from the user.

Step 2: Check for Divide-by-Zero Errors

- Iterate through the diagonal elements of the matrix a (from a[0][0] to a[n-1][n-1]).
- Check if any of the diagonal elements are zero. If a zero is found, exit the program with an error message ("Divide by zero detected!).

Step 3: Perform Gaussian Elimination

- Iterate through the rows of the matrix a (from row 0 to row n-2).
- For each row i, iterate through the rows below it (from row i+1 to row n-1).
- Calculate the ratio of the element at position [j][i] to the element at position [i][i].
- Subtract the product of this ratio and the entire row i from row j.

Step 4: Perform Back Substitution

- Initialize the solution variable x[n-1] with the value of the last element in the last row of the matrix a divided by the diagonal element in the last row.
- Iterate through the remaining rows of the matrix a in reverse order (from row n-2 to row 0).
- For each row i, calculate the value of the solution variable x[i] by subtracting the sum of the products of the elements in the current row and the previously calculated solution variables from the constant term in the current row. Then, divide the result by the diagonal element in the current row.

Step 5: Print the Solution

- Print the values of the solution variables x[0] to x[n-1], rounded to two decimal places.

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

