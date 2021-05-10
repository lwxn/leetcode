```c++
class Solution {
public:
    string replaceSpace(string s) {
        for(int i = 0;i<s.size();i++)
        {
            if(s[i] == ' ')
            {
                s = s.substr(0,i)+"%20"+s.substr(i+1,s.size()-i-1);
                i+=2;
            }
        }
        return s;
    }
};
```

