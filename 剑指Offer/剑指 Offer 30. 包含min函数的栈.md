```c++
class MinStack {
public:
    /** initialize your data structure here. */
    stack<int>s;
    stack<int>help;
    MinStack() {

    }
    
    void push(int x) {
        s.push(x);
        if (help.empty() || help.top() >= x) help.push(x);
    }
    
    void pop() {
        if(!s.empty())
        {
            if(help.top() == s.top()) help.pop();
            s.pop();
        }
    }
    
    int top() {
        return s.top();
    }
    
    int min() {
        return help.top();
    }
};

/**
 * Your MinStack object will be instantiated and called as such:
 * MinStack* obj = new MinStack();
 * obj->push(x);
 * obj->pop();
 * int param_3 = obj->top();
 * int param_4 = obj->min();
 */
```

