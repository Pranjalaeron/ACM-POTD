**Next Greater Element I**
```
class Solution {
public:
    vector<int> nextGreaterElement(vector<int>& nums1, vector<int>& nums2) {
        int N=nums1.size();
        vector<int>ans(N);
        int n=nums2.size();
        stack<int>st;
        unordered_map<int,int>m;
        for(int i=n-1;i>=0;i--){
            if(!st.empty()){
                while(!st.empty() && st.top()<=nums2[i]){
                    st.pop();
                }
                if(st.empty()){
                    m[nums2[i]]=-1;
                    st.push(nums2[i]);
                }
                else{
                    m[nums2[i]]=st.top();
                    st.push(nums2[i]);
                }
            }
            else{
                m[nums2[i]]=-1;
                st.push(nums2[i]);
            }

        }
        for(int i=0;i<nums1.size();i++){
            ans[i]=(m[nums1[i]]);
        }
        return ans;
    }
};
```
<img width="1470" height="835" alt="image" src="https://github.com/user-attachments/assets/c19d705d-dc37-4520-ab96-f6be719e33e8" />


