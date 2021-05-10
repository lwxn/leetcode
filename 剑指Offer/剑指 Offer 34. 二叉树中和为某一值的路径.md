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
private:
    vector<vector<int>>ans;
public:
    vector<vector<int>> pathSum(TreeNode* root, int sum) {
        find(root,0,sum,vector<int>(0));
        return ans;
    }
    
    void find(TreeNode* root,int value,int target,vector<int>v)
    {
        if(!root) return;
        
        v.push_back(root->val);
        value += root->val;
        //cout<<root->val<<" "<<value<<endl;
        
        if(!root->left && !root->right)
        {
            if(value == target) 
            {
                ans.push_back(v);
            }
            return;
        }
        
        find(root->left,value,target,v);
        find(root->right,value,target,v);
    }
};
```

