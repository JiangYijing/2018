# Bulb Switcher
## 问题分析：
灯泡开关,n个灯泡中第一次打开所有灯泡,第二次每两个更改灯泡的状态,……第n次每n个更改灯泡的状态,求n次后所有亮的灯泡的个数
## 编程实现：
```C++
class Solution {
public:
    int bulbSwitch(int n)
    {
        int res=1;
        while(res*res<=n) 
        ++res;
        return res-1;
    }
};
```
