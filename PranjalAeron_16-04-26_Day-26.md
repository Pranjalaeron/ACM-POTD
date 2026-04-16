**Invert Binary Tree**
```
class Solution {
public:
    TreeNode* invertTree(TreeNode* root) {
        if(root==NULL) return root;
        
        TreeNode*temp=root->right;
        root->right=root->left;
        root->left=temp;

        invertTree(root->left);
        invertTree(root->right);

        return root;        

    }
};
```
<img width="1470" height="835" alt="image" src="https://github.com/user-attachments/assets/4a59ece2-d433-4385-897e-10f2d32a278e" />

**Kth Smallest Element in a BST**
```
class Solution {
public:
    void inorder(TreeNode*root,vector<int>&vec){
        if(root==NULL) return;
        inorder(root->left,vec);
        vec.push_back(root->val);
        inorder(root->right,vec);
        }
    int kthSmallest(TreeNode* root, int k) {
        vector<int>vec;
        inorder(root,vec);
        if(k>vec.size()) return -1;
        return vec[k-1];
        
    }
};
```
<img width="1470" height="833" alt="image" src="https://github.com/user-attachments/assets/29df5e0d-1943-4ec1-b8f5-d52f4b2221ec" />
