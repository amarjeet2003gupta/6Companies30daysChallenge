# Airplane Seat Assignment Probability

Problem Link : [Link](https://leetcode.com/problems/airplane-seat-assignment-probability/description/)

Solution Link : [Link](https://leetcode.com/problems/airplane-seat-assignment-probability/submissions/871899587/)

**Solution:-**
```C++

class Solution {
public:
    double nthPersonGetsNthSeat(int n) {
        return 1/(double)min(n,2);
    }
};


```
