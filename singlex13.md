#  Base 7
## 问题分析：
基数七,将给定数字转为七进制,且可正可负。
## 编程实现：
```C++
class Solution {
public:
    string convertToBase7(int num) {
        if(num==0)
        return "0";
        string res="";
        bool positive=num>0;
        while(num!=0) 
        {
            res=to_string(abs(num%7))+res;
            num/=7;
        }
        return positive?res:"-"+res;
    }
};
```
