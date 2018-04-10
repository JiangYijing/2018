# Integer Break
## 问题分析：
将整数n拆分成至少两个正整数之和,使其乘积最大,主要是找规律
## 编程实现：
```C++
class Solution {
public:
    int integerBreak(int n) {
        if (n == 2 || n == 3) return n - 1;
        int res = 1;
        while (n > 4) {
            res *= 3;
            n -= 3;
        }
        return res * n;
    }
};
```
