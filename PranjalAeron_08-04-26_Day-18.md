**Remove All Adjacent Duplicates In String**
```
class Solution {
public:
    string removeDuplicates(string s) {
        int n=s.length();
        string ans="";
        for(int i=0;i<n;i++){
            if(!ans.empty() && s[i]==ans.back()){
                ans.pop_back();
            }
            else{
                ans.push_back(s[i]);
            }
        }
        return ans;
    }
};
```
<img width="1470" height="828" alt="image" src="https://github.com/user-attachments/assets/987ba8b4-44a0-44fd-9cf5-8815f22e2cd2" />

**Next Greater Element II**
```
class Solution {
public:
    vector<int> nextGreaterElements(vector<int>& nums) {
        int n=nums.size();
        vector<int>ans(n,-1);
        stack<int>st;
        for(int i=2*n-1;i>=0;i--){
            while(!st.empty() && st.top()<=nums[i%n]){
                st.pop();
            }
            if(!st.empty()){
                ans[i%n]=st.top();
            }
            
            st.push(nums[i%n]);
            
        
        }
        return ans;
        
        
        
    }
};
```
<img width="1470" height="835" alt="image" src="https://github.com/user-attachments/assets/06a6dc25-f12b-4ee8-a974-4ce38d0be555" />
