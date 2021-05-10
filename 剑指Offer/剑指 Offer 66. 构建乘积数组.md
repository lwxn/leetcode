```c++
class Solution {
public:
    vector<int> constructArr(vector<int>& a) {
        vector<int>l(a.size(),1);
        vector<int>r(a.size(),1);
        vector<int>b(a.size());
        
        for(int i = 0;i<a.size();i++)
        {
            l[i] = i == 0 ? a[0] : l[i-1]*a[i];
            r[a.size()-1-i] = i == 0 ? a[a.size()-1-i] : r[a.size()-i]*a[a.size()-1-i]; 
        }

        if(a.size()>=2)
        {
            b[0] = r[1];
            b[a.size()-1] = l[a.size()-2];
        }
            
        
        int len = a.size();
        for(int i = 1;i<len-1;i++)
        {
            b[i] = l[i-1]*r[i+1];
        }
        return b;
        
    }
};
```

