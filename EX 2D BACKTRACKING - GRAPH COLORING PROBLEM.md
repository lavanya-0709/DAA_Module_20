# EX 2D BACKTRACKING - GRAPH COLORING PROBLEM
## DATE: 11/03/2025
## AIM:
To solve the Graph Coloring Problem using backtracking, assigning colors to the vertices of a graph such that no two adjacent vertices share the same color while minimizing the number of colors used.



## Algorithm
1.Try to assign colors (from 1 to m) to each vertex one by one.

2.Before assigning a color to a vertex, check if it's safe (no adjacent vertex has the same color).

3.If a safe color is found, assign it and move to the next vertex recursively.

4.If no color can be assigned to a vertex, backtrack and change previous color choices.

5.If all vertices are successfully colored, print the solution.

6.If not, report that no valid coloring exists.

## Program:
```
/*
Program to implement Graph Coloring Problem using backtracking.
Developed by: LAVANYA S
Register Number: 212223230112
*/
class Graph():
 
    def __init__(self, vertices):
        self.V = vertices
        self.graph = [[0 for column in range(vertices)]for row in range(vertices)]
 
  
    def isSafe(self, v, colour, c):
        for i in range(self.V):
            if self.graph[v][i] == 1 and colour[i] == c:
                return False
        return True
     
    
    def graphColourUtil(self, m, colour, v):
        if v==self.V:
            return True
        for c in range(1,m+1):
            if self.isSafe(v,colour,c):
                colour[v]=c
                if self.graphColourUtil(m,colour,v+1):
                    return True
                colour[v]=c
        return False
        #############Add your code here ##############
 
    def graphColouring(self, m):
        colour=[0]*self.V
        if not self.graphColourUtil(m,colour,0):
            print("Nosolution Exist")
            return False
       #----------------Add your code here ---------------
 
        # Print the solution
        print ("Solution exist and Following are the assigned colours:")
        for c in colour:
            print (c,end=' ')
        return True

```

## Output:
![image](https://github.com/user-attachments/assets/59ff3968-a918-4522-907e-40b69110c81c)


## Result:
The Graph Coloring program executed successfully, and the colors were assigned to the vertices such that no two adjacent vertices share the same color.
