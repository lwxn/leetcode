```c++
class Solution {
public:
    bool verifyPostorder(vector<int>& postorder) {
        return verify(postorder,0,postorder.size()-1);
    }
    
    bool verify(vector<int>postorder,int i,int j)
    {
        if(i<j)
        {
            int p = j;
            int m = j;
            for(int k = i;k<=j;k++)
            {
                if(postorder[k] > postorder[p])
                {
                    m = k;
                    break;
                }
            }

            for(int k = m+1;k<p;k++)
            {
                if(postorder[k] <= postorder[p]) return false;
            }
            return verify(postorder,i,m-1) && verify(postorder,m,j-1);
        }
        return true;
    }
};
```

