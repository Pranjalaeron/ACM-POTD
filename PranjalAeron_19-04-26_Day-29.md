**Fibonacci Number**
```
class Solution {
public:
    int fib(int n) {
        if(n==0) return 0;
        if(n==1) return 1;
        return fib(n-1)+fib(n-2);
    }
};

```
<img width="1468" height="834" alt="image" src="https://github.com/user-attachments/assets/9d81dca1-68e1-4b6e-ad1f-6e20d26ffbf1" />

**Subsets**
```

class Solution {
private:
    void sub(vector<int>& nums, vector<vector<int>>&ans, vector<int>&temp, int i){
        int n=nums.size();
        if(i==n){
            ans.push_back(temp);
            return;
        }
        sub(nums,ans,temp,i+1);
        temp.push_back(nums[i]);
        sub(nums,ans,temp,i+1);
        temp.pop_back();
    }
public:
    vector<vector<int>> subsets(vector<int>& nums) {
        vector<vector<int>>ans;
        vector<int>temp;
        sub(nums,ans,temp,0);
        return ans;
    }
};
```
<img width="1470" height="830" alt="image" src="https://github.com/user-attachments/assets/dcc78f53-fe76-4d6d-8207-cb144cab43f5" />

