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
    TreeNode* buildTree(vector<int>& preorder, vector<int>& inorder) {
        return build(preorder,inorder,0,0,preorder.size()-1);
    }
    
    TreeNode* build(vector<int>& preorder, vector<int>& inorder,int root,int begin,int end)
    {
        if(begin <= end)
        {
            TreeNode* head = new TreeNode(preorder[root]);
            int i = begin;
            while(i<=end && preorder[root]!=inorder[i])
            {   
                i++;
            }
            head->left = build(preorder,inorder,root+1,begin,i-1);
            head->right = build(preorder,inorder,root+i-begin+1,i+1,end);
            return head;
        }
        return NULL;
    }
};
```

