```c++
class Solution {
public:
    int lengthOfLongestSubstring(string s) {
        int ans = 0;
        set<char>ss;
        int i = 0;
        for(int j = 0;j<s.size();)
        {
            while(j<s.size() && !ss.count(s[j]))
            {
                ss.insert(s[j++]);
            }
            ans = max(ans,(int)(ss.size()));
            if(j<s.size())
            {
                while(ss.count(s[j]))
                {
                    ss.erase(s[i++]);
                }
                ss.insert(s[j++]);
            }
        }
        return ans;
    }
};
```

