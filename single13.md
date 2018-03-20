# Multiply Strings
## 问题分析：
大整数相乘,将每一位都相乘,然后从低位起依次进位,结果中注意去掉0的情况、
## 编程实现：
```C++
class Solution {
public:
    string multiply(string num1, string num2) {
        int n1=num1.size(),n2=num2.size();
        vector<int> tmpres(n1+n2,0);
        int k=n1+n2-2;
        for(int i=0;i<n1;i++)
            for(int j=0;j<n2;j++)
                tmpres[k-i-j]+=(num1[i]-'0')*(num2[j]-'0');
        int carryBit=0;
        for(int i=0;i<n1+n2;i++)
        {
            tmpres[i]+=carryBit;
            carryBit=tmpres[i]/10;
            tmpres[i]%=10;
        }
        int i=k+1;
        while(tmpres[i]==0) i--;
        if(i<0)  return "0";
        string res;
        for( ;i>=0;i--)
            res.push_back(tmpres[i]+'0');
        return res;
    }
};
```
