# EX 2A BACKTRACKING - RAT IN MAZE PROBLEM
## DATE: 04/03/2025
## AIM:
To implement the Rat in a Maze problem using backtracking and find all possible paths from the start to the destination in a given maze.


## Algorithm
1.Start at the top-left cell (0,0) of the maze.

2.At each step, check if the current cell is safe (value 1 and within bounds).

3.Mark the cell as part of the path and try moving down or right recursively.

4.If reaching the bottom-right cell (destination), mark it and return success.

5.If moving forward is not possible, backtrack by unmarking the cell.

6.Print the final path if a solution exists; otherwise, report no solution.
  

## Program:
```
/*
Program to implement Rat in a Maze.
Developed by: LAVANYA S
Register Number: 212223230112
*/
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
     
    # Creating a 4 * 4 2-D list
    sol = [ [ 0 for j in range(4) ] for i in range(4) ]
     
    if solveMazeUtil(maze, 0, 0, sol) == False:
        print("Solution doesn't exist");
        return False
     
    printSolution(sol)
    return True
     

def solveMazeUtil(maze, x, y, sol):
    if x == N - 1 and y == N - 1:
        sol[x][y] = 1
        return True
    if isSafe(maze,x,y)==True:
        sol[x][y]=1
        if solveMazeUtil(maze,x+1,y,sol)==True:
            return True
        if solveMazeUtil(maze,x,y+1,sol) ==True:
            return True
        sol[x][y]=0
        return False
   

if __name__ == "__main__":
    # Initialising the maze
    maze = [ [1, 0, 0, 0],
             [1, 1, 0, 1],
             [0, 1, 0, 0],
             [1, 1, 1, 1] ]
              
    solveMaze(maze)
```

## Output:
![image](https://github.com/user-attachments/assets/0b52bc40-8d04-404e-9eb0-ad55f433c61e)


## Result:
The Rat in a Maze program executed successfully, and a valid path from the start to the destination was found and display.
