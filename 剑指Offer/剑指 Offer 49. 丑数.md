```c++
class Solution {
public:
    int nthUglyNumber(int n) {
        vector<int>num(n,0);
        num[0] = 1;
        int i = 0,j = 0,k = 0;
        int idx = 1;
        
        while(idx < n)
        {
            int tmp =  min(num[i]*2,min(num[j]*3,num[k]*5));
            num[idx++] = tmp;
            if(tmp == num[i]*2) i++;
            if(tmp == num[j]*3) j++;
            if(tmp == num[k]*5) k++;
        }
        return num[idx-1];
    }
};
```

