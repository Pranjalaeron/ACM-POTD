**Remove Duplicates from Sorted List**
```
class Solution {
public:
    ListNode* deleteDuplicates(ListNode* head) {
        if(head==NULL || head->next==NULL) return head;
        ListNode*dummy=new ListNode(-1);
        ListNode*res=dummy;
        ListNode*temp=head;

        res->next=new ListNode(temp->val);
        temp=temp->next;
        res=res->next;

        while(temp){
            if(temp->val!=res->val){
                res->next=new ListNode(temp->val);
                res=res->next;
            }
            temp=temp->next;
        }
        return dummy->next;
    }
};
```
<img width="1470" height="835" alt="image" src="https://github.com/user-attachments/assets/bf4d41f0-ed7c-4770-ba55-f2d21eecc547" />

**Rotate List**
```
class Solution {
public:
    ListNode* rotateRight(ListNode* head, int k) {
        if(!head || !head->next || k==0) return head;

        ListNode*temp=head;
        int cnt=0;
        while(temp){
            cnt++;
            temp=temp->next;
        }
        temp=head;
        
        k=k%cnt;
        if(k==0) return head;
        int n=cnt-k-1;

        while(n--){
            temp=temp->next;
        }
        ListNode*curr=temp->next;
        temp->next=NULL;

        ListNode*main=curr;
        while(main->next){
            main=main->next;
        }
        ListNode*temp2=head;
        main->next= temp2;
        return curr;


    }
};
```
<img width="1469" height="833" alt="image" src="https://github.com/user-attachments/assets/a33876ae-a47e-4c70-b574-41f3e7b9084d" />
