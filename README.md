# JavaWeb
**暴力使用**
```
class Solution {
public:
    vector<int> twoSum(vector<int>& nums, int target) {
        vector<int> ans;
        for(int i = 0;i < nums.size();i++){
            int t = target-nums[i];
            for(int j = i+1;j<nums.size();j++){
                if(t == nums[j]){
                    ans.push_back(i);
                    ans.push_back(j);
                    return ans;
                }
            }
        }
        return ans;
    }
};
```
**hashtable遍历一次过**
```
class Solution {
public:
    vector<int> twoSum(vector<int>& nums, int target) {
        unordered_map<int,int> map;
        vector<int> b;
        for(int i = 0;i < nums.size();i++){
            int t = target-nums[i];
            if(map.count(t)>0){
                b.push_back(map[t]);
                b.push_back(i);
                return b;
            }
            map[nums[i]] = i;
        }
        return b;
    }
};
```
