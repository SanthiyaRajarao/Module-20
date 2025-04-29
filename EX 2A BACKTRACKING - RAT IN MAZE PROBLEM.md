# EX 2A BACKTRACKING - RAT IN MAZE PROBLEM
## DATE: 03/03/25
## AIM:
To implement the Rat in a Maze problem using backtracking and find all possible paths from the start to the destination in a given maze.


## Algorithm
### ✅ Short Algorithm for Rat in a Maze (Backtracking)

1. Create a solution matrix of the same size as the maze.  
2. Begin from the top-left cell `(0, 0)`.  
3. Move to a cell only if it's within bounds and value is `1`.  
4. Try moving right or down recursively.  
5. If both moves fail, backtrack by marking the cell as `0`. If destination is reached, print the solution.

## Program:
```
/*
Program to implement Rat in a Maze.
Developed by: SANTHIYA R
Register Number: 212223230192
*/
```
```
N = 4
def printSolution( sol ):
     
    for i in sol:
        for j in i:
            print(str(j) + " ", end ="")
        print("")
 

def isSafe( maze, x, y ):
     
    if x >= 0 and x < N and y >= 0 and y < N and maze[x][y] == 1:
        return True
    return False
 

def solveMaze( maze ):
    sol = [ [ 0 for j in range(4) ] for i in range(4) ]
    if solveMazeUtil(maze, 0, 0, sol) == False:
        print("Solution doesn't exist");
        return False
    printSolution(sol)
    return True
     

def solveMazeUtil(maze, x, y, sol):
    if x==N-1 and y==N-1 and maze[x][y]==1:
        sol[x][y]=1
        return True
    if isSafe( maze, x, y ):
        sol[x][y]=1
        if solveMazeUtil(maze, x+1, y, sol):
            return True
        if solveMazeUtil(maze, x, y+1, sol):
            return True
        sol[x][y]=0
    return False
    
if __name__ == "__main__":
    maze = [ [1, 0, 0, 0],
             [1, 1, 0, 1],
             [0, 1, 0, 0],
             [1, 1, 1, 1] ]
              
    solveMaze(maze)
```

## Output:

![image](https://github.com/user-attachments/assets/6ee28ed0-d55a-450d-9580-b2d725e07e2e)


## Result:
The Rat in a Maze program executed successfully, and a valid path from the start to the destination was found and display.
