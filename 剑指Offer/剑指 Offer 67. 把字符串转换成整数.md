```c++
class Solution {
public:
    int strToInt(string str) {
        int i = 0;
        while(str[i] == ' ') i++;
        
        int flag = 0;
        long num = 0;
        if(str[i] == '-')
        {
            flag = 1;
            i++;
        }
        else if(str[i] == '+')
        {
            flag = 0;
            i++;
        }
        if(isdigit(str[i]))
        {
            while(i < str.size() && isdigit(str[i]))
            {
                if(num >INT_MAX) break;
                num = num*10 + str[i] - '0';
                i++;
            }
            if(flag) num = -num;
            if(num > INT_MAX) return INT_MAX;
            if(num < INT_MIN) return INT_MIN;
            return num;
        }
        return 0;
        
    }
};
```

