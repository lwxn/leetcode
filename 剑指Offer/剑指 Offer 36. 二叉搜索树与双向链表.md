```c++
/*
// Definition for a Node.
class Node {
public:
    int val;
    Node* left;
    Node* right;

    Node() {}

    Node(int _val) {
        val = _val;
        left = NULL;
        right = NULL;
    }

    Node(int _val, Node* _left, Node* _right) {
        val = _val;
        left = _left;
        right = _right;
    }
};
*/
class Solution {
public:
    Node* H = new Node(0),*pre = NULL,*cur = NULL;
    Node* treeToDoublyList(Node* root) {
        if(!root) return NULL;
        cur = root;
        dfs(root);
        cur->right = H;
        H->left = cur;
        return H;
    }

    void dfs(Node* root)
    {
         if(root)
        {
            treeToDoublyList(root->left);  
            if(!pre)
            {
                pre = root;
                H = pre;
            }
            else
            {
                cur = root;
                cur->left = pre;
                pre->right = cur;
                pre = cur;
            }
            treeToDoublyList(root->right);
        }
    }
};
```

