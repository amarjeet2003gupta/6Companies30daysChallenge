# Minimum Deletions to Make Array Divisible

Problem Link : [Link](https://leetcode.com/problems/minimum-deletions-to-make-array-divisible/description/)

Solution Link : [Link](https://leetcode.com/problems/minimum-deletions-to-make-array-divisible/submissions/871908457/)

**Solution:-**
```C++

class Solution {
public:
    int minOperations(vector<int>& nums, vector<int>& numsDivide) {
        int gcd = 0;
        for(auto i : numsDivide) gcd = __gcd(gcd,i);
        multiset<int> mst;
        for(auto i : nums) mst.insert(i);
        auto it = mst.begin();
        int ct = 0;
        while(it!=mst.end() && *it<gcd){
            if(__gcd(*it,gcd)==*it) return ct;
            it++;
            ct++;
        }
        if(it==mst.end() || *it!=gcd) return -1;
        return ct;
    }
};

```
