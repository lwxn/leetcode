```c++
class Solution {
public:
    string reverseLeftWords(string s, int n) {
        string s1 = s.substr(0,n);
        s = s+s1;
        return s.substr(n,s.size()-n);
    }
};
```

