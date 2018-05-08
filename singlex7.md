# Elimination Game
## 问题分析：
淘汰游戏,利用递归从左往右和从右往左遍历
## 编程实现：
```C++
class Solution {
public:
    int lastRemaining(int n){
        return help(n,true);    
    }
    int help(int n,bool left2right) {
        if(n==1) return 1;
        if(left2right) {
            return 2*help(n/2,false);
        } 
        else
        {
            return 2*help(n/2,true)-1+n%2;
        }
    }
};
```
