# EX 2B BACKTRACKING - NQUEEN PROBLEM
## DATE: 03/03/25
## AIM:
To solve the N-Queen problem using backtracking, which places N queens on an N*N chessboard such that no two queens threaten each other.


## Algorithm

1. Read size `N` for the board.  
2. Ensure no queen can attack others (check rows, columns, diagonals).  
3. Try placing queens in columns recursively.  
4. If placement leads to a dead-end, remove the queen and try next row.  
5. Print the solution if found, else state no solution exists. 

## Program:
```
/*
Program to implement N-Queen problem using backtracking.
Developed by: SANTHIYA R
Register Number: 212223230192
*/
```
```
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
![image](https://github.com/user-attachments/assets/607d37eb-3be0-481c-993a-92d7e75dc90a)
      if col>=N:
          return True
      for i in range(N):
          if isSafe(board, i, col):
              board[i][col]=1
              if solveNQUtil(board, col+1):
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

![image](https://github.com/user-attachments/assets/839a4166-f1b0-4628-8302-3494f8ab39f0)



## Result:
The N-Queens program executed successfully, and a valid board configuration was generated.
