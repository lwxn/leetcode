```c++
class Solution {
public:
    bool static cmp(const string & a,const string & b)
    {
        return a+b < b+a;
    }
    string minNumber(vector<int>& nums) {
        vector<string>v;
        string ans = "";
        for(int num : nums)
        {
            v.push_back(to_string(num));
        }
        sort(v.begin(),v.end(),cmp);
        for(string s:v)
        {
            ans += s;
        }
        return ans;
    }
};
```

