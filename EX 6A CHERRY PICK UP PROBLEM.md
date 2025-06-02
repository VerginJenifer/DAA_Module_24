# EX 6A CHERRY PICK UP PROBLEM
## DATE:
## AIM:
To Create a python program for the following problem statement.
You are given an n x n grid representing a field of cherries, each cell is one of three possible integers.
0	means the cell is empty, so you can pass through,
1	means the cell contains a cherry that you can pick up and pass through, or
-1 means the cell contains a thorn that blocks your way.
Return the maximum number of cherries you can collect by following the rules below:
Starting at the position (0, 0) and reaching (n - 1, n - 1) by moving right or down through valid path cells (cells with value 0 or 1).
After reaching (n - 1, n - 1), returning to (0, 0) by moving left or up through valid path cells.
When passing through a path cell containing a cherry, you pick it up, and the cell becomes an empty cell 0. If there is no valid path between (0, 0) and (n - 1, n - 1), then no cherries can be collected.



## Algorithm
1. Define a recursive function dp(k) that calculates max cherries collected starting from row k.
2. At the last row, return the cherries picked by two robots at all column pairs (count once if both on same cell).
3. For each row k, compute maximum cherries for all pairs of robot positions (i, j).
4. For each possible move of both robots (left, down, right), update ans[i][j] with max cherries collected including current row.
5. Return dp(0)[0][COL_NUM-1], the max cherries starting from row 0 with robots at columns 0 and last.  

## Program:
```
/*
To implement the program for Cherry pickup problem.


Developed by: 
Register Number:
class Solution(object):
    def cherryPickup(self, grid):
        def dp(k):
            
            if k == ROW_NUM - 1:
                return [[grid[-1][i] if i == j else grid[-1][i] + grid[-1][j] for j in range(COL_NUM)]
                        for i in range(COL_NUM)]
            row = grid[k]
            ans = [[0] * COL_NUM for i in range(COL_NUM)]
            next_dp = dp(k + 1)
            for i in range(COL_NUM):
                for j in range(i, COL_NUM):
                    for di in [-1, 0, 1]:
                        for dj in [-1, 0, 1]:
                            if 0 <= i + di < COL_NUM and 0 <= j + dj < COL_NUM:
                                if i == j:
                                    ans[i][j] = max(ans[i][j], next_dp[i + di][j + dj] + row[i])
                                else:
                                    ans[i][j] = max(ans[i][j], next_dp[i + di][j + dj] + row[i] + row[j])
            return ans
            
        ROW_NUM = len(grid)
        COL_NUM = len(grid[0])
        return dp(0)[0][COL_NUM - 1]
        
grid=[[3,1,1],
      [2,5,1],
      [1,5,5],
      [2,1,1]]
ob=Solution()
print(ob.cherryPickup(grid))
*/
```

## Output:

![image](https://github.com/user-attachments/assets/ed406dbb-a57a-482b-8b2d-80f068654ff6)


## Result:
Thus the above program was executed successfully for finding the maximum number of cherries from grid.
