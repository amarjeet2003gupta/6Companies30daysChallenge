# Combination Sum with a twist

Problem Link : [Link](https://leetcode.com/problems/combination-sum-iii/description/)

Solution Link : [Link](https://leetcode.com/problems/combination-sum-iii/submissions/871174721/)

**Solution:-**
```C++

class Solution {
public:
    vector<vector<int>> ans;
    void call(vector<int> &temp,int n,int k,int number){
        if(number>9){
            if(n==0 && temp.size()==k) ans.push_back(temp);
            return;
        }
        if(number<=n){
            temp.push_back(number);
            call(temp,n-number,k,number+1);
            temp.pop_back();
        }
        call(temp,n,k,number+1);
    }
    vector<vector<int>> combinationSum3(int k, int n) {
        if(n<k) return ans;
        vector<int> temp;
        int number = 1;
        call(temp,n,k,number);
        return ans;
    }
};

```
