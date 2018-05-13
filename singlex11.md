# Arranging Coins 
## 问题分析:
将n枚硬币排列成阶梯状,找出可形成完整阶梯行的总行数
## 编程实现:
```C++
class Solution {
public:
    int arrangeCoins(int n) {
        int cur=1,retain=n-1;
        while(cur+1<=retain)
        {
            ++cur;
            retain-=cur;
        }
        return n==0?0:cur;
    }
};
```
