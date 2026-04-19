**Subtree of Another Tree**
```
class Solution {
public:
    bool isSubtree(TreeNode* root, TreeNode* sub) {
        if (!root) return false;
        if (isSame(root,sub)) return true;
    return isSubtree(root->left,sub)||isSubtree(root->right,sub);
}
    bool isSame(TreeNode* s,TreeNode* t){
        if(!s&&!t)return true; if(!s||!t)return false;
    return s->val==t->val&&isSame(s->left,t->left)&&isSame(s->right,t->right);
    }
};
```
 <img width="1465" height="788" alt="image" src="https://github.com/user-attachments/assets/ccaae6a1-f5ac-4166-91ca-d8a12d2c9ae3" />
