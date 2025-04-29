# EX 2D BACKTRACKING - GRAPH COLORING PROBLEM
## DATE: 04/03/25
## AIM:
To solve the Graph Coloring Problem using backtracking, assigning colors to the vertices of a graph such that no two adjacent vertices share the same color while minimizing the number of colors used.

## Algorithm

1. Read number of vertices `V` and adjacency matrix `graph`.  
2. For each vertex, try assigning colors (from 1 to `m`) and check if it's safe (i.e., no two adjacent vertices have the same color).  
3. If a valid color assignment exists for a vertex, recursively try to color the next vertex.  
4. If all vertices are successfully colored, return the color configuration.  
5. If a valid coloring exists, print the colors; otherwise, print "Solution does not exist".

## Program:
```
/*
Program to implement Graph Coloring Problem using backtracking.
Developed by: SANTHIYA R
Register Number: 212223230192
*/
```
```
class Graph:
    def __init__(self, vertices):
        self.V = vertices
        self.graph = [[0 for _ in range(vertices)] for _ in range(vertices)]

    def isSafe(self, v, colour, c):
        for i in range(self.V):
            if self.graph[v][i] and colour[i] == c:
                return False
        return True

    def graphColoringUtil(self, m, colour, v):
        if v == self.V:
            return True

        for c in range(1, m + 1):
            if self.isSafe(v, colour, c):
                colour[v] = c
                if self.graphColoringUtil(m, colour, v + 1):
                    return True
                colour[v] = 0
        return False  # Return False if no valid coloring is possible

    def graphColouring(self, m):
        colour = [0] * self.V
        if not self.graphColoringUtil(m, colour, 0):
            print("Solution does not exist")
            return
        
        return colour
            
g = Graph(4)
g.graph = [
    [0, 1, 1, 1],
    [1, 0, 1, 0],
    [1, 1, 0, 1],
    [1, 0, 1, 0]
]
m = 3
colors = g.graphColouring(m)

if colors:
    print("Solution exist and Following are the assigned colours:")
    for c in colors:
        print(c, end=" ")
    print()

```

## Output:

![image](https://github.com/user-attachments/assets/0beb0c02-df22-44d0-9579-b57f4187947c)


## Result:
The Graph Coloring program executed successfully, and the colors were assigned to the vertices such that no two adjacent vertices share the same color.
