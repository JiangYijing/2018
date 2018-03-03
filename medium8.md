# Longest Palindromic Substring
## 问题分析：
最长的回文数列,从遍历位置从中间向两边判断
## 编程实现：
```C++
public class Solution 
{
    public String longestPalindrome(String s) 
    {
       if(s.length() <= 1) return s;
       int max=0;
       String res = new String();
       for(int i=0;i<s.length();i++)
       {
           int L=i,R=i;
           String temp=getPlength(s,L,R);
           if(temp.length() > max)
           {
               max = temp.length();
               res = new String(temp);
           }
           if(i!=s.length()-1)
           {
               L = i; R = i + 1;
               temp = getPlength(s,L,R);
               if(temp.length() > max)
               {
                   max = temp.length();
                   res = new String(temp);
               }
           }
       }
       return res;
    }
    public String getPlength(String s, int L , int R)
    {
        while(L >= 0 && R < s.length() && s.charAt(L) == s.charAt(R))
        {
            L--;R++;
        }
        return s.substring(L+1,R);
    }
}
```

# Pow(x, n)
## 问题分析：
求x的n次方,运用递归折半计算
## 编程实现：
```C++
class Solution {
public:
    double myPow(double x, int n) {
        if(n < 0) return 1/power(x, -n);
        return power(x, n);
    }
    double power(double x,int n) 
    {
        if(n==0) return 1;
        double half=power(x,n/2);
        if(n % 2==0) return half*half;
        return x*half*half;
    }
};
```
```
