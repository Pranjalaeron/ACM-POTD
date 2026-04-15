**Maximum Depth of Binary Tree**
```
class Solution {
public:
    int maxDepth(TreeNode* root) {
        if(root==NULL) return 0;
        return 1+ max(maxDepth(root->left), maxDepth(root->right));
    }
};
```
<img width="1470" height="831" alt="image" src="https://github.com/user-attachments/assets/1d917c55-a140-439c-a969-66478bfcefed" />


**Binary Tree Level Order Traversal**
```
class Solution {
public:
    vector<vector<int>> levelOrder(TreeNode* root) {
        if(root==NULL) return {};
        vector<vector<int>>ans;
        queue<TreeNode*>q;
        q.push(root);
        while(!q.empty()){
            int size=q.size();
            vector<int>temp;
            for(int i=0;i<size;i++){
                TreeNode* node=q.front();
                q.pop();
                temp.push_back(node->val);

                if(node->left) q.push(node->left);
                if(node->right) q.push(node->right);
            }
            ans.push_back(temp);
            
        }
        return ans;

            
    }
};
```
<img width="1470" height="831" alt="image" src="https://github.com/user-attachments/assets/3af159c2-943b-4205-95dc-2e78f3a7bc6e" />

