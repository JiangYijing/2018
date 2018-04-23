# Power of Two
## 问题分析:
给定一个整数,写一个函数判断它是否是2的若干次幂。
## 编程实现:
```C++
class Solution {
public:
    bool isPowerOfTwo(int n) {
        int cnt=0;
        while(n>0) 
        {
            cnt+=(n&1);
            n>>=1;
        }
        return cnt==1;
    } 
};
```
