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
    vector<vector<int>> levelOrder(TreeNode* root) {
        
        vector<vector<int>>ans;
        if(!root) return ans;

        queue<TreeNode*>q;
        q.push(root);
        int flag = 0;
        while(!q.empty())
        {
            vector<int>v;
            int len = q.size();
            if(flag == 0)
            {          
                for(int i = 0;i<len;i++)
                {
                    TreeNode* t = q.front();
                    q.pop();
                    if(t)
                    {
                        v.push_back((int)(t->val));
                        if(t->left);
                            q.push(t->left);
                        if(t->right)
                            q.push(t->right);
                    }
                    
                }
            }
            else
            {
                for(int i = 0;i<len;i++)
                {
                    TreeNode* t = q.front();
                    q.pop();
                    if(t)
                    {
                        v.push_back((int)(t->val));
                        if(t->left);
                            q.push(t->left);
                        if(t->right)
                            q.push(t->right);
                    }
                }
                reverse(v.begin(),v.end());
            }
            flag = (flag+1)%2;
            if(!v.empty())
                ans.push_back(v);
        }
        return ans;
    }
};
```

