
# All Elements in Two Binary Search Trees

Problem Link : [Link](https://leetcode.com/problems/all-elements-in-two-binary-search-trees/)

Solution Link : [Link](https://leetcode.com/problems/all-elements-in-two-binary-search-trees/submissions/880721908/)

**Solution:-**
```C++

/**
 * Definition for a binary tree node.
 * struct TreeNode {
 *     int val;
 *     TreeNode *left;
 *     TreeNode *right;
 *     TreeNode() : val(0), left(nullptr), right(nullptr) {}
 *     TreeNode(int x) : val(x), left(nullptr), right(nullptr) {}
 *     TreeNode(int x, TreeNode *left, TreeNode *right) : val(x), left(left), right(right) {}
 * };
 */
class Solution {
public:
    void call(TreeNode *root, vector<int> &a){
        if(!root) return;
        a.push_back(root->val);
        call(root->left,a);
        call(root->right,a);
    }
    vector<int> getAllElements(TreeNode* root1, TreeNode* root2) {
        vector<int> a;
        call(root1,a);
        call(root2,a);
        sort(a.begin(),a.end());
        return a;
    }
};


```
