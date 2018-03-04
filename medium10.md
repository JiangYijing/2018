# Spiral Matrix
## 问题分析：
矩阵按照螺旋顺序打印,对每个环的边进行顺序打印
## 编程实现：
```C++
class Solution {
public:
    vector<int> spiralOrder(vector<vector<int> > &matrix) {
        vector<int> res;
        if(matrix.empty()||matrix[0].empty()) return res;
        int m=matrix.size(),n=matrix[0].size();
        int c=m>n ? (n+1)/2:(m+1)/2;
        int p=m,q=n;
        int i=0;
        for(i=0;i<c;++i,p-=2,q-=2)
        {
            for(int col=i;col<i+q;++col) 
                res.push_back(matrix[i][col]);
            for(int row=i+1;row<i+p;++row)
                res.push_back(matrix[row][i + q - 1]);
            if(p==1||q==1)  break;
            for(int col=i+q-2;col>=i;--col)
                res.push_back(matrix[i + p - 1][col]);
            for (int row=i+p-2;row>i;--row) 
                res.push_back(matrix[row][i]);
        }
        return res;
    }
};
```

# Jump Game
## 问题分析：
动态规划题目,注意有局部解和最终解
## 编程实现：
```C++
class Solution {
public:
    bool canJump(vector<int>& nums) {
    if (nums.length == 0)   return false;
    int maxCover=0,step=1; 
    for(int i=0;i<nums.length;i++)
    { 
        step--;
        if(i+nums[i]>maxCover)
        { 
            maxCover=i+nums[i];
            step=nums[i]; 
        } 
        if(step==0 && i<nums.length-1) 
            return false;
    } 
        return true; 
    }
};
```
