# Add Digits
## 问题分析:
加数字,即求数根,就是将大于10的数的各个位上的数字相加,若结果还大于0的话,则继续相加,直到数字小于10为止
## 编程实现:
```C++
class Solution {
public:
    int addDigits(int num) 
    {
        while(num/10> 0)
        {
            int sum=0;
            while(num>0)
            {
                sum+=num%10;
                num/=10;
            }
            num=sum;
        }
        return num;
    }
};
```
