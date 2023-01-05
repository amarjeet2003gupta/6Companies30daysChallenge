# Shortest Unsorted Continuous Subarray

Problem Link : [Link](https://leetcode.com/problems/shortest-unsorted-continuous-subarray/description/)

Solution Link : [Link](https://leetcode.com/problems/shortest-unsorted-continuous-subarray/submissions/871874432/)

**Solution:-**
```C++

class Solution {
public:
    int findUnsortedSubarray(vector<int>& nums) {
        vector<int> a = nums;
        sort(a.begin(),a.end());
        int ct = 0;
        for(int i=0;i<nums.size();i++){
            if(nums[i]!=a[i]) break;
            ct++;
        }
        int ct2 = 0;
        for(int i=nums.size()-1;i>=ct;i--){
            if(nums[i]!=a[i]) break;
            ct2++;
        }
        return a.size()-ct-ct2;
    }
};


```
