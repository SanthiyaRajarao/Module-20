# EX 2C BACKTRACKING - SUBSET SUM PROBLEM
## DATE: 04/03/25
## AIM:
To demonstrate that the sum of the subset of a given set is equal to the given sum.


## Algorithm

1. Read array and target sum `sum`.  
2. For each element, either include or exclude it and adjust the sum.  
3. If all elements are considered, check if the sum is zero and count it.  
4. Count the valid subsets.  
5. Print the total number of subsets that sum to the target.
6. 
## Program:
```
/*
Program to implement Subset sum problem.
Developed by: SANTHIYA R
Register Number: 212223230192
*/
```
```
def subsetSum(arr,n,i,sum,count):
    if(i==n):
        if(sum==0):
            count+=1
        return count
    count=subsetSum(arr,n,i+1,sum-arr[i],count)
    count=subsetSum(arr,n,i+1,sum,count)
    return count
    
arr=[]
size=int(input())
for j in range(size):
    value=int(input())
    arr.append(value)
sum=int(input())
n=len(arr)
print(subsetSum(arr,n,0,sum,0))
```

## Output:

![image](https://github.com/user-attachments/assets/19f63d2b-93b3-4fc6-9edd-486f865f5308)


## Result:
The Subset Sum program executed successfully, and the result was determined based on whether a subset matching the target sum was found or not.
