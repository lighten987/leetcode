# leetcode
一天一道leetcode，先ac，再比较最优解法
  
1.两数之和  
class Solution {  
public:  
    vector<int> twoSum(vector<int>& nums, int target) {  
       vector<int> out;  
       for(int i = 0 ; i < nums.size() ; ++i){  
           int m = target - nums[i];  
           for(int j = i+1 ; j < nums.size(); ++j){  
               if(nums[j]==m){  
                   out.push_back(i);  
                   out.push_back(j);  
                   break;  
               }  
           }  
       }  
        return out;  
    }  
};  
执行用时: 192 ms, 在Two Sum的C++提交中击败了10.58% 的用户  


