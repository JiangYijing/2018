# Integer Break
## 问题分析：
整数拆分,主要是观察规律。
## 编程实现：
```C++
class Solution {
public:
    int integerBreak(int n) {
        if(n==2||n==3) 
        return n-1;
        int res=1;
        while(n>4) 
        {
            res*=3;
            n-=3;
        }
        return res*n;
    }
};
```
