```c++
/*
// Definition for a Node.
class Node {
public:
    int val;
    Node* next;
    Node* random;
    
    Node(int _val) {
        val = _val;
        next = NULL;
        random = NULL;
    }
};
*/
class Solution {
public:
    Node* copyRandomList(Node* head) {
        if(!head) return NULL;
        // copy.
        Node *p = head;
        while(p)
        {
            Node* tmp = new Node(p->val);
            tmp->next = p->next;
            p->next = tmp;
            p = tmp->next;
        }
        // random.
        Node* p1 = head, *p2 = head->next;
        while(p1)
        {
            p2 = p1->next;
            if(p1->random) p2->random =  p1->random->next;
            p1 = p2->next;
            
        }
        // cut.
        Node* ans = head->next;
        p1 = head;
        p2 = head->next;
        while(p1)
        {
            // head.
            p1->next = p1->next->next;
            p1 = p1->next;
            // p1.
            if(p2->next)
            {
                p2->next = p1->next;
                p2 = p2->next;
            }
            
        }
        return ans;
    }

    void print(Node* p)
    {
        while(p)
        {
            cout<<p->val<<" ";
            p = p->next;
        }
        cout<<endl;
    }
};
```

