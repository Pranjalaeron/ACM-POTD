**Check if N and Its Double Exist**
```
class Solution {
public:
    bool checkIfExist(vector<int>& arr) {
        int n=arr.size();
        unordered_set<int>st;
        int zerocnt=0;
        for(int i:arr){
            if(i==0) zerocnt++;
            st.insert(i);
        }

        bool flag=false;
        for(int i:arr){
            if(zerocnt==1){
                if(i!=0 && st.find(2*i)!=st.end()){
                    flag=true;
                }
            }
            else{
                if(st.find(2*i)!=st.end()){
                    flag=true;
                }
            }
        }
        return flag;
    }
};
```
<img width="1468" height="832" alt="image" src="https://github.com/user-attachments/assets/92ad8878-2987-409b-bd42-c143dd3de34a" />

**Continuous Subarray Sum**
```
class Solution {
public:
    bool checkSubarraySum(vector<int>& nums, int k) {
        unordered_map<int, int> mp;
        mp[0] = -1; 
        int sum = 0;
        for (int i = 0; i < nums.size(); i++) {
            sum += nums[i];
            int rem = (k == 0) ? sum : sum % k;
            if (mp.find(rem) != mp.end()) {
                if (i - mp[rem] >= 2) {
                    return true;
                }
            } 
            else {
                mp[rem] = i;
            }
        }
        return false;
    }
};
```
<img width="1469" height="832" alt="image" src="https://github.com/user-attachments/assets/273f8a48-4edb-4bb5-b134-9567bf752a7e" />

**Candy**
```
class Solution {
public:
    int candy(vector<int>& ratings) {
        int n = ratings.size();
        vector<int> candies(n, 1);
        for (int i = 1; i < n; i++) {
            if (ratings[i] > ratings[i - 1]) {
                candies[i] = candies[i - 1] + 1;
            }
        }
        for (int i = n - 2; i >= 0; i--) {
            if (ratings[i] > ratings[i + 1]) {
                candies[i] = max(candies[i], candies[i + 1] + 1);
            }
        }
        int total = 0;
        for (int c : candies) total += c;
        return total;
    }
};
```
<img width="1468" height="831" alt="image" src="https://github.com/user-attachments/assets/24144ca8-8289-4cb3-b467-b602a028afe6" />
