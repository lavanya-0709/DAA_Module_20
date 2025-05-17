=# EX 2B BACKTRACKING - NQUEEN PROBLEM
## DATE: 08/03/2025
## AIM:
To solve the N-Queen problem using backtracking, which places N queens on an N*N chessboard such that no two queens threaten each other.


## Algorithm
1.Start placing queens column by column, beginning from the leftmost column.

2.For each column, try placing a queen in all rows one by one.

3.Before placing, check if it's safe (no queens on the same row, upper diagonal, or lower diagonal on the left side).

4.If placing a queen is safe, mark that cell and move to the next column recursively.

5.If placing the queen leads to a solution, return success; otherwise, backtrack and remove the queen.

6.If all queens are placed correctly, print the board; otherwise, state that no solution exists.
 

## Program:
```
/*
Program to implement N-Queen problem using backtracking.
Developed by: LAVANYA S
Register Number: 212223230112
*/
global N
N = int(input())
 
def printSolution(board):
    for i in range(N):
        for j in range(N):
            print(board[i][j], end = " ")
        print()
 
def isSafe(board, row, col):
 
    # Check this row on left side
    for i in range(col):
        if board[row][i] == 1:
            return False
 
    # Check upper diagonal on left side
    for i, j in zip(range(row, -1, -1),
                    range(col, -1, -1)):
        if board[i][j] == 1:
            return False
 
    # Check lower diagonal on left side
    for i, j in zip(range(row, N, 1),
                    range(col, -1, -1)):
        if board[i][j] == 1:
            return False
 
    return True
 
def solveNQUtil(board, col):
    if col>=N:
        return True
    for i in range(N):
        if isSafe(board,i,col):
            board[i][col]=1
            if solveNQUtil(board,col+1):
                return True
            board[i][col]=0
    return False
        
      
def solveNQ():
    board = [ [0, 0, 0, 0],
              [0, 0, 0, 0],
              [0, 0, 0, 0],
              [0, 0, 0, 0]]
              
    if solveNQUtil(board, 0) == False:
        print ("Solution does not exist")
        return False
 
    printSolution(board)
    return True
 
# Driver Code
solveNQ()

```

## Output:

![image](https://github.com/user-attachments/assets/6d5be4d8-5600-47e3-9c1a-1827d7db9f9f)


## Result:
The N-Queens program executed successfully, and a valid board configuration was generated.
