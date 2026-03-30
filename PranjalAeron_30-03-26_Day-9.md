**Linked List Cycle**
```
class Solution {
public:
    bool hasCycle(ListNode *head) {
        if(head==NULL || head->next==NULL) return false;
        ListNode *slow=head;
        ListNode *fast=head;
        while(fast!=NULL && fast->next!=NULL){
            slow=slow->next;
            fast=fast->next->next;
            if(slow==fast) return true;
        }
        return false;
    }
};
```
<img width="1470" height="831" alt="image" src="https://github.com/user-attachments/assets/fe4aa0fb-791d-4b4e-beec-6307f6df4cf1" />

**Linked List Cycle II**
```
class Solution {
public:
    ListNode *detectCycle(ListNode *head) {
       if(!head || !(head->next)) return NULL;
       ListNode *slow=head;
       ListNode *fast=head;
       while(fast!=NULL && fast->next!=NULL){
        slow=slow->next;
        fast=fast->next->next;
        if(slow==fast) break;
        }
        if(slow!=fast) return NULL;
        slow=head;
        while(slow!=fast){
            slow=slow->next;
            fast=fast->next;
        }
        return slow;
    }
};
```
<img width="1470" height="828" alt="image" src="https://github.com/user-attachments/assets/58d52250-27d2-408c-813f-e92dd667a349" />

