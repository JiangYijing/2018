#  Unique Binary Search Trees
## 问题分析：
关于卡塔兰数,形成二叉搜索树
## 编程实现：
```C++
class Solution {
public:
    int numTrees(int n) {
        vector<int> dp(n+1,0);
        dp[0]=1;
        dp[1]=1;
        for(int i=2;i<=n;++i)
        {
            for(int j=0;j<i;++j) 
            {
                dp[i]+=dp[j]*dp[i-j-1];
            }
        }
        return dp[n];
    }
};
```
