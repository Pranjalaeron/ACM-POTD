**Intersection of Two Linked Lists**
```
class Solution {
public:
    ListNode *getIntersectionNode(ListNode *headA, ListNode *headB) {
        if(!headA || !headB) return NULL;
        ListNode*temp1=headA;
        ListNode*temp2=headB;
        while(temp1 != temp2){
            if(temp1==NULL){
                temp1=headB;
            }
            else{
                temp1=temp1->next;
            }
            if(temp2==NULL){
                temp2=headA;
            }
            else{
                temp2=temp2->next;
            }
            
            
        }
        return temp1;
    }
};
```
<img width="1470" height="832" alt="image" src="https://github.com/user-attachments/assets/96f0986a-56f8-4d08-94a6-5808de33ec1e" />

**Remove Duplicates from Sorted List II**
```
lass Solution {
public:
    ListNode* deleteDuplicates(ListNode* head) {
        if(!head || !head->next) return head;
        ListNode*dummy=new ListNode(0);
        dummy->next=head;
        ListNode*prev=dummy;
        while(prev->next && prev->next->next){
            if(prev->next->val==prev->next->next->val){
                int duplicate=prev->next->val;
                while(prev->next && prev->next->val==duplicate){
                    prev->next=prev->next->next;
                }
            }
            else{
                prev=prev->next;
            }
        }
        return dummy->next;
    }
};
```
<img width="1468" height="836" alt="image" src="https://github.com/user-attachments/assets/3631e5a3-df7f-4a40-945d-d422791f060b" />


