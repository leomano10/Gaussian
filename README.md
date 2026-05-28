# Gaussian Elimination

## AIM:
To write a program to find the solution of a matrix using Gaussian Elimination.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Moodle-Code Runner

## Algorithm
1. Import the required packages.
2.Read the augmented matrix values.
3.Apply Gaussian Elimination to convert the matrix into upper triangular form.
4.Perform back substitution and print the solution.


## Program:
'''Program to solve a matrix using Gaussian elimination without partial pivoting.
Developed by: manorajapriyan.l.e
RegisterNumber: 212225040227
'''
n = int(input())

a = []

for i in range(n):
    row = []
    for j in range(n + 1):
        row.append(float(input()))
    a.append(row)

x = [0 for i in range(n)]

for i in range(n):

    for j in range(i + 1, n):

        ratio = a[j][i] / a[i][i]

        for k in range(n + 1):
            a[j][k] = a[j][k] - ratio * a[i][k]

x[n - 1] = a[n - 1][n] / a[n - 1][n - 1]

for i in range(n - 2, -1, -1):

    x[i] = a[i][n]

    for j in range(i + 1, n):
        x[i] = x[i] - a[i][j] * x[j]

    x[i] = x[i] / a[i][i]

for i in range(n):
    print("X{} = {:.2f}".format(i, x[i]), end=" ")

## Output:



## Result:
Thus the program to find the solution of a matrix using Gaussian Elimination is written and verified using python programming.

