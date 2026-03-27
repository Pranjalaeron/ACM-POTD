**Move Zeroes**
```
class Solution {
public:
    void moveZeroes(vector<int>& nums) {
       int n=nums.size();
       int i=0, j=0;
       while(j<n){
        if(nums[j]!=0){
            swap(nums[i],nums[j]);
            i++;
        }
        j++;
       }
    }
};
```
<img width="1470" height="826" alt="image" src="https://github.com/user-attachments/assets/98a91f68-d036-4661-9d39-ddf5aefc33ab" />




**Product of Array Except Self**
```
class Solution {
public:
    vector<int> productExceptSelf(vector<int>& nums) {
        int n=nums.size();
        vector<int>prefix;
        vector<int>suffix;
        prefix.push_back(1);
        int product=1;
        for(int i:nums){
            product*=i;
            prefix.push_back(product);
        }
        prefix.pop_back();
        int prod=1;
        suffix.push_back(prod);
        for(int i=n-1;i>=0;i--){
            prod*=nums[i];
            suffix.push_back(prod);
        }
        suffix.pop_back();
        reverse(suffix.begin(),suffix.end());
        vector<int>ans;
        for(int i=0;i<n;i++){
            ans.push_back(prefix[i]*suffix[i]);
        }
        return ans;
    }
};
```
<img width="1470" height="835" alt="image" src="https://github.com/user-attachments/assets/49a6b8a7-90f4-4178-a095-d3feb1b8217b" />



**Sliding Window Maximum**
```
class Solution {
public:
    vector<int> maxSlidingWindow(vector<int>& nums, int k) {
        priority_queue<pair<int, int>> pq;
        vector<int> res;
        for (int i = 0; i < k; i++) {
            pq.push(make_pair(nums[i], i));
        }
        res.push_back(pq.top().first);
        
        for (int i = k; i < nums.size(); i++) {
            while (!pq.empty() && pq.top().second <= i - k) {
                pq.pop();
            }
            pq.push(make_pair(nums[i], i));
            res.push_back(pq.top().first);
        }
        return res;
    }
};
```

<img width="1470" height="833" alt="image" src="https://github.com/user-attachments/assets/e93f6cc7-94f5-4973-8794-24d1e3e13d75" />
