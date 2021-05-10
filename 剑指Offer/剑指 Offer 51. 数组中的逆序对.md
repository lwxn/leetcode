```c++
class Solution {
public:
    int cnt = 0;
    int reversePairs(vector<int>& nums) {
        mergesort(nums,0,nums.size()-1);
        return cnt;
    }

    void mergesort(vector<int>&nums,int l,int r)
    {
        if(l<r)
        {
            vector<int>tmp(r-l+1);
            int i = l,mid = (l+r)>>1;
            int j = mid+1;
            int p = 0;

            mergesort(nums,l,mid);
            mergesort(nums,mid+1,r);

            while(i <= mid || j <= r)
            {
                if(j > r || i <= mid && nums[i] <= nums[j])
                {
                    tmp[p++] = nums[i++];
                }
                else
                {
                    tmp[p++] = nums[j++];
                    cnt += mid - i + 1;
                }
            }

            for(int k = 0;k<tmp.size();k++)
            {
                nums[l + k] = tmp[k]; 
            }
        }
    }
};
```

