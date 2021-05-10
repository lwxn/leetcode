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
    bool isSymmetric(TreeNode* root) {
        if(!root) return true;
        return mirror(root->right,root->left);
    }
    
    bool mirror(TreeNode* root1,TreeNode* root2)
    {
        if(!root1&&!root2) return true;
        if(root1 && root2)
        {
            return root1->val == root2->val && mirror(root1->left,root2->right)
                && mirror(root1->right,root2->left);
        }
        return false;
    }
};
```

