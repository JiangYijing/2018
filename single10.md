# Evaluate Reverse Polish Notation
## 问题分析：
计算逆波兰表达式,操作数前置,操作符后置,前面的数和运算符运算完后需要删去然后加入新的数到原数组中
## 编程实现：
```C++
class Solution {
public:
    int evalRPN(vector<string> &tokens) {
        if(tokens.size()==1) return atoi(tokens[0].c_str());
        stack<int> s;
        for(int i=0;i<tokens.size();++i)
    {
            if (tokens[i] != "+" && tokens[i]!="-"&& tokens[i]!="*"&&tokens[i]!="/") 
　　　　　　　{
                s.push(atoi(tokens[i].c_str()));
            } 
         else
            {
                int m=s.top();
                s.pop();
                int n=s.top();
                s.pop();
                if(tokens[i] == "+") s.push(n + m);
                if(tokens[i] == "-") s.push(n - m);
                if(tokens[i] == "*") s.push(n * m);
                if(tokens[i] == "/") s.push(n / m);
            }
        }
        return s.top();
    }
};
```
