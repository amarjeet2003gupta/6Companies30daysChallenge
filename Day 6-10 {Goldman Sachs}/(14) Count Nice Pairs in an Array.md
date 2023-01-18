
# Count Nice Pairs in an Array

Problem Link : [Link](https://leetcode.com/problems/count-nice-pairs-in-an-array/)

Solution Link : [Link](https://leetcode.com/problems/count-nice-pairs-in-an-array/submissions/880784486/)

**Solution:-**
```C++

class Solution {
public:
    const int mod = 1e9+7;
    int countNicePairs(vector<int>& nums) {
        vector<int> rev;
        for(auto &i : nums){
            int k = i;
            int num = 0;
            while(k){
                num = num*10 + (k%10);
                k /= 10;
            }
            rev.push_back(num);
        }
        map<int,int> m;
        for(int i=0;i<nums.size();i++){
            m[nums[i]-rev[i]]++;
        }
        
        long long ans = 0;
        for(auto i : m){
            ans = (ans + ((long)i.second*((long)i.second-1)/2)) % mod;
        }
        return (int)ans;
    }
};

```
