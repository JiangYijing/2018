# Restore IP Addresses
## 问题分析：
运用递归,首先判断后续的字符串长度是否在规定长度内。
## 编程实现：
```C++
class Solution {
public:
    vector<string> restoreIpAddresses(string s) {
        vector<string> result;
        vector<int> pos(4,0);
        find(0,0,s,pos,result);
        return result;
    }
    void find(int start,int deep,string &s,vector<int> &pos,vector<string> &result)
    {
        if(s.size()-start>(4-deep)*3||s.size()-start<4-deep)
            return;
        if(deep==4 && start==s.size())
        {
            int beg=0;
            string addr;
            for(int i=0;i<4;i++)
            { 
                string ip(s,beg,pos[i]-beg+1);
                beg=pos[i]+1;
                addr+=i==0?ip:'.'+ip;
            }
            result.push_back(addr);
        }
        for(int i=start;i<s.size();i++)
        {
            if(check(start,i,s))
            {
                pos[deep]=i;
                find(i+1,deep+1,s,pos,result);                
            }
        }
    }
     bool check(int start,int index,string &s)
     { 
        string ip(s,start,index-start+1);
        if(ip.size()==1)
            return "0"<=ip && ip<="9";
        else if(ip.size()==2)
            return "10"<=ip && ip<="99";
        else if(ip.size()==3)
            return "100"<=ip && ip<="255";
        else 
            return false;
    }
};
```
