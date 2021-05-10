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
        
        queue<TreeNode* >q;
        q.push(root);
        while(!q.empty())
        {
            vector<int>tmp;
            int m = q.size();
            for(int i = 0;i<m;i++)
            {
                tmp.push_back(q.front()->val);
                if(q.front()->left) q.push(q.front()->left);
                if(q.front()->right) q.push(q.front()->right);
                
                q.pop();
            }
            ans.push_back(tmp);
        }
        return ans;
    }
};
```

