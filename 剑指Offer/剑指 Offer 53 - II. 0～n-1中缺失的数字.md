```c++
class Solution {
public:
    int missingNumber(vector<int>& nums) {
        int left = 0;
        int right = nums.size();
        while(left<right)
        {
            int mid = (left+right)/2;
            if(nums[mid] == mid) left = mid+1;
            else if(nums[mid]>mid) right = mid;
        }
        return right;
    }
};
```

