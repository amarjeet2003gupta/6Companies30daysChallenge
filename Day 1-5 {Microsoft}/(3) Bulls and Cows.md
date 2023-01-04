# Bulls and Cows

Problem Link : [Link](https://leetcode.com/problems/bulls-and-cows/description/)

Solution Link : [Link](https://leetcode.com/problems/bulls-and-cows/submissions/871194830/)

**Solution:-**
```C++

class Solution {
public:
    string getHint(string secret, string guess) {
        map<char,int> a,b;
        int x=0,y=0;
        for(int i=0;i<secret.size();i++){
            if(secret[i]==guess[i]) x++;
            else{
                a[secret[i]]++;
                b[guess[i]]++;
            }
        }
        for(char i='0';i<='9';i++) y += min(a[i],b[i]);
        string s;
        s += to_string(x);
        s += "A";
        s += to_string(y);
        s += "B";
        return s;
    }
};

```
