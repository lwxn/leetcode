```c++
/**
 * Definition for a binary tree node.
 * struct TreeNode {
 *     int val;
 *     TreeNode *left;
 *     TreeNode *right;
 *     TreeNode(int x) : val(x), left(NULL), right(NULL) {}
 * };
 */
class Solution {
public:
    int ans = 0,count = 0;
    int kthLargest(TreeNode* root, int k) {
        dfs(root,k);
        return ans;
    }
    
    void dfs(TreeNode* root,int k)
    {
        if(root && count < k)
        {
            dfs(root->right,k);
            count++;
            if(count == k) ans = root->val;
            dfs(root->left,k);
        }
        
    }
};
```

