```c++
class MaxQueue {
public:
    queue<int>q;
    deque<int>help;
    MaxQueue() {
        
    }
    
    int max_value() {
        return help.empty() ? -1 : help.front();
    }
    
    void push_back(int value) {
        q.push(value);
        while(!help.empty() && help.back() < value)
        {
            help.pop_back();
        }
        help.push_back(value);
    }
    
    int pop_front() {
        if(q.empty()) return -1;
        int value = q.front();
        q.pop();
        if(help.front() == value)
        {
            help.pop_front();
        }
        return value;
    }
};

/**
 * Your MaxQueue object will be instantiated and called as such:
 * MaxQueue* obj = new MaxQueue();
 * int param_1 = obj->max_value();
 * obj->push_back(value);
 * int param_3 = obj->pop_front();
 */
```

