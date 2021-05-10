```c++
class Solution {
public:
    string reverseWords(string s) {
        stringstream ss(s);
        vector<string>ans;
        while(ss>>s)
        {
            ans.push_back(s);
        }
        
        reverse(ans.begin(),ans.end());
        s = ans.size()>=1 ? ans[0] : "";
        for(int i = 1;i<ans.size();i++) s += " " + ans[i];
        return s;
    }
};
```

