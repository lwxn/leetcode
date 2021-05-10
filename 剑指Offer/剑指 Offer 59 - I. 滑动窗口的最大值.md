```c++
class Solution {
public:
    vector<int> maxSlidingWindow(vector<int>& nums, int k) {
        vector<int>ans;
        deque<int>q;
        for(int i = 0;i<k;i++)
        {
            while(!q.empty() && q.back() < nums[i]) q.pop_back();
            q.push_back(nums[i]);
        }
        if(!q.empty()) ans.push_back(q.front());
        for(int i = k;i<nums.size();i++)
        {
            //delete
            if(!q.empty() && q.front() == nums[i-k]) q.pop_front();

            while(!q.empty() && q.back() < nums[i]) q.pop_back();
            q.push_back(nums[i]);
            ans.push_back(q.front());
        }
        return ans;
    }
};
```

