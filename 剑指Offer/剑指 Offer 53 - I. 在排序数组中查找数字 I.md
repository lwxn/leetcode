```c++
class Solution {
public:
    int search(vector<int>& nums, int target) {
        int l = 0;
        int r = nums.size()-1;
        while(l<r)
        {
            int m = (l+r)/2;
            if(target <= nums[m]) r = m;
            else l = m+1;
        }
        
        int ans = 0;
        while(l<nums.size() && target == nums[l])
        {
            ans++;
            l++;
        }
        return ans;
    }
};
```

