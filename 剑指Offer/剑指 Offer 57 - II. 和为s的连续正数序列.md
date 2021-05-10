```c++
class Solution {
public:
    vector<vector<int>> findContinuousSequence(int target) {
        vector<vector<int>>ans;
        int l = 1, r = 2;
        int sum = l+r;
        vector<int>t;
        
        while(l<r)
        {
            if(sum == target)
            {
                t.clear();
                for(int i = l;i<=r;i++) t.emplace_back(i);
                ans.push_back(t);
                sum-=l;
                l++;
            }
            else if(sum < target)
            {
                r++;
                sum+=r;
            }
            else
            {
                sum-=l;
                l++;
            }
        }
        return ans;
    }
};
```

