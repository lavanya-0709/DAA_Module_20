# EX 2C BACKTRACKING- SUBSET SUM PROBLEM
## DATE: 08/03/2025
## AIM:
To demonstrate that the sum of the subset of a given set is equal to the given sum.


## Algorithm
1.Start with the first element and an initial sum of 0.

2.At each step, you have two choices: include the current element in the sum or exclude it.

3.If the current sum equals the target, return True (subset found).

4.If the index goes out of bounds or the sum exceeds the target, return False.

5.Recursively check both including and excluding the current element.

6.If any path returns True, a subset with the given sum exists; otherwise, it doesn't. 
   

## Program:
```
/*
Program to implement Subset sum problem.
Developed by: LAVANYA S
Register Number: 212223230112
*/
def SubsetSum(a,i,sum,target,n):

    if target==sum:
        return True
    if i>=n or sum>target:
        return False
    if SubsetSum(a,i+1,sum+a[i],target,n):
        return True
    if SubsetSum(a,i+1,sum,target,n):
        return True
    return False
a=[]
size=int(input())
for i in range(size):
    x=int(input())
    a.append(x)

target=int(input())
n=len(a)
if(SubsetSum(a,0,0,target,n)==True):
    for i in range(size):
        print(a[i])
    print("True,subset found")
else:
    for i in range(size):
        print(a[i])
    print("False,subset not found")

```

## Output:

![image](https://github.com/user-attachments/assets/927a2e16-6a18-439c-8827-4b875e02ef7c)


## Result:
The Subset Sum program executed successfully, and the result was determined based on whether a subset matching the target sum was found or not.
