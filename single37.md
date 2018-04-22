# Count  Primes
## 问题分析:
求出小于n的数中共有多少个质数,可以考虑使用动态数组表示小于n的每个元素是否为质数来提高效率。
## 编程实现:
```C++
class Solution {
public:
    int countPrimes(int n) {
        if(n<=2) return 0;
        bool *p=new bool[n];
        memset(p,true,sizeof(bool)*n);
        for(int i=2;i*i<n;i++)
        {
            if(p[i])
            {
                for(int j=2;j*i<n;j++)
                    p[i*j]=false;
            }
        }
        int cnt=0;
        for(int i=2;i!=n;i++)
            if(p[i])   cnt++;
        delete[]p;
        return cnt;
    }
};
```

