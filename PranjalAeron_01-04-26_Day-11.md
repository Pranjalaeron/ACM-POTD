**Merge Two Sorted Lists**
```
class Solution {
public:
    ListNode* mergeTwoLists(ListNode* head1, ListNode* head2) {
        ListNode*temp1=head1;
        ListNode*temp2=head2;
        ListNode* dummy=new ListNode(-1);
        ListNode*res=dummy;

        while(temp1 && temp2){
            if(temp1->val<=temp2->val){
                res->next=temp1;
                res=res->next;
                temp1=temp1->next;
            }
            else{
                res->next=temp2;
                res=res->next;
                temp2=temp2->next;
            }
        }

        while(temp1){
            res->next=temp1;
            res=res->next;
            temp1=temp1->next;
        }
        while(temp2){
            res->next=temp2;
            res=res->next;
            temp2=temp2->next;
        }
        return dummy->next;


    }
};
```
<img width="1470" height="833" alt="image" src="https://github.com/user-attachments/assets/21099f6b-0d80-4da3-af60-ffcb5face6a9" />

