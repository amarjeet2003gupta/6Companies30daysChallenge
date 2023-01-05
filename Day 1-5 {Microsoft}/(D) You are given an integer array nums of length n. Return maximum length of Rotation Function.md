# Bulls and Cows

Problem Link : [Link](https://leetcode.com/problems/rotate-function/description/)

Solution Link : [Link](https://leetcode.com/problems/rotate-function/submissions/871218993/)

**Solution:-**
```C++

class Solution {
public:
    int maxRotateFunction(vector<int>& nums) {
        int n = nums.size();
        int total = accumulate(nums.begin(),nums.end(),0);
        
        int mx = 0;
        total -= nums[0];
        for(int i=0;i<n;i++) mx += (i*nums[i]);
        int sum = mx;
        for(int i=1;i<n;i++){
            sum -= total;
            sum += (n-1)*nums[i-1];
            total += nums[i-1];
            total -= nums[i];
            mx = max(mx,sum);
        }
        return mx;
    }
};

```
