# Evaluate Reverse Polish Notation 

Problem Link : [Link](https://leetcode.com/problems/evaluate-reverse-polish-notation/)

Solution Link : [Link](https://leetcode.com/problems/evaluate-reverse-polish-notation/submissions/869874042/)

**Solution:-**
```C++

class Solution {
public:
    int evalRPN(vector<string>& tokens) {
        stack<long long> st;
        for(auto i : tokens){
            if(i!="+" && i!="-" && i!="*" && i!="/") st.push(stoi(i));
            else{
                long a = st.top(); st.pop();
                long b = st.top(); st.pop();
                if(i=="+") b += a;
                if(i=="-") b -= a;
                if(i=="*") b *= a;
                if(i=="/") b /= a;
                st.push(b);
            }
        }
        return (int)st.top();
    }
};


```
