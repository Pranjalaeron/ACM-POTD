**Diameter of Binary Tree**
```
class Solution {
public:
    int diameter=0;
    int maxDepth(TreeNode*root){
        if(root==NULL) return 0 ;
        int lh=maxDepth(root->left);
        int rh=maxDepth(root->right);
        diameter=max(diameter, lh+rh);
        return 1+max(lh,rh);
        
    }
    int diameterOfBinaryTree(TreeNode* root) {
        if(root==NULL || (root->left==NULL && root->right==NULL)) return 0;
        maxDepth(root);
        return diameter;
        

    }
    
};
```
<img width="1470" height="835" alt="image" src="https://github.com/user-attachments/assets/968e2885-66e8-47a8-9468-1033e00d6d1d" />
