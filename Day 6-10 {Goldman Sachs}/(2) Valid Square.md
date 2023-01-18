
# Valid Square

Problem Link : [Link](https://leetcode.com/problems/valid-square/)

Solution Link : [Link](https://leetcode.com/problems/valid-square/submissions/874286521/)

**Solution:-**
```C++

class Solution {
public:
    int euclidean_distance(int x1,int y1,int x2,int y2)
    {
        int a=(x2-x1)*(x2-x1);
        int b=(y2-y1)*(y2-y1);
        return a+b;
    }
    bool validSquare(vector<int>& p1, vector<int>& p2, vector<int>& p3, vector<int>& p4) {
        vector<vector<int>> a;
        a.push_back(p1);
        a.push_back(p2);
        a.push_back(p3);
        a.push_back(p4);

        set<int> s;
        for(int i=0;i<4;i++){
            for(int j=i+1;j<4;j++){
                int d = euclidean_distance(a[i][0],a[i][1],a[j][0],a[j][1]);
                if(d==0) return false;
                else s.insert(d);
            }
        }
        if(s.size()>2) return false;
        return true;
    }
};


```
