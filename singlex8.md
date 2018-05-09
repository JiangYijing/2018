# Nth Digit
## 问题分析：
第N位,自然数序列看成一个长字符串,求第N位上的数字即找出第N位所在的数字,然后把数字转为字符串
## 编程实现：
```C++
class Solution {
public:
    int findNthDigit(int n) {
        long long len=1,cnt=9,start=1;
        while(n>len*cnt) 
        {
            n-=len*cnt;
            ++len;
            cnt*=10;
            start*=10;
        }
        start+=(n-1)/len;
        string t=to_string(start);
        return t[(n-1)%len]-'0';
    }
};
```
