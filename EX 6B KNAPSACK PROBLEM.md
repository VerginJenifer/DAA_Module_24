# EX 6B KNAPSACK PROBLEM
## DATE:
## AIM:
To demonstrate a python program using dynamic programming for 0/1 knapsack problem.



## Algorithm
1. Create a 2D dp array of size (n+1) x (W+1) initialized to zero.
2. For each item i from 1 to n and weight w from 0 to W:
3. If the item’s weight is less than or equal to w, set dp[i][w] = max(value of item + dp[i-1][w - item_weight], dp[i-1][w]).
4. Otherwise, copy the value from dp[i-1][w] (exclude the item).
5. Return dp[n][W], the maximum value achievable with n items and capacity W.

## Program:
```
/*
To implement the program for 0/1 knapsack problem.


Developed by: D Vergin Jenifer
Register Number: 212223240174
def knapSack(W, wt, val, n):
    dp = [[0 for x in range(W + 1)] for x in range(n + 1)]
    for i in range(n + 1):
        for w in range(W + 1):
            if i == 0 or w == 0:
                dp[i][w] = 0 
            elif wt[i - 1] <= w:
                dp[i][w] = max(val[i - 1] + dp[i - 1][w - wt[i - 1]],dp[i - 1][w])
            else:
                dp[i][w] = dp[i - 1][w]
    return dp[n][W]


x=int(input())
y=int(input())
W=int(input())
val=[]
wt=[]
for i in range(x):
    val.append(int(input()))
for y in range(y):
    wt.append(int(input()))
n = len(val)
print('The maximum value that can be put in a knapsack of capacity W is: ',knapSack(W, wt, val, n))
*/
```

## Output:

![image](https://github.com/user-attachments/assets/451c0388-0e50-4187-a694-a4dec43b954e)


## Result:
Thus the program was executed successfully for finding the maximum value that can be put in a knap sack of capacity .
