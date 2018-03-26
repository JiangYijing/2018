# Unique Paths
## 问题分析:
每一条路要么往下走要么往右走,若能到达终点就return 1,要不然就返回0,递归实现运算
## 编程实现：
```C++
public int uniquePaths(int m,int n) {
        return uniquePaths(1,1,m,n);
    }
    public int uniquePaths(int currentRow,int currentColumn,int m,int n){
        if(currentRow==m||currentColumn==n)
        {
            return 1;
        }    
        return uniquePaths(currentRow+1,currentColumn,m,n)+uniquePaths(currentRow,currentColumn+1,m,n);
    }
```


#  Unique Paths II
## 问题分析：
加入障碍物,尝试用动态规划来解题,当遇到为1点时,将数组中值清零。
## 编程实现：
```C++
class Solution {
public:
    int uniquePathsWithObstacles(vector<vector<int>>& obstacleGrid) {
        if(obstacleGrid.empty()||obstacleGrid[0].empty()||obstacleGrid[0][0]==1)  return 0;
        vector<vector<int>>dp(obstacleGrid.size(),vector<int>(obstacleGrid[0].size(),0));
        for(int i=0;i<obstacleGrid.size();++i)
        {
            for(int j=0;j<obstacleGrid[i].size();++j)
            {
                if(obstacleGrid[i][j]==1) dp[i][j]=0;
                else if(i==0&&j==0) dp[i][j]=1;
                else if(i==0&&j>0) dp[i][j]=dp[i][j-1];
                else if(i>0&&j==0) dp[i][j]=dp[i-1][j];
                else dp[i][j]=dp[i-1][j]+dp[i][j-1];
            }
        }
        return dp.back().back();
    }
};
```
