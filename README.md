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
  
2.两数相加（未ac）  
class Solution {
public:
    ListNode* addTwoNumbers(ListNode* l1, ListNode* l2) {
        ListNode* l;
        for(int i = 0 ; ; ++i){
            while(l1!=NULL || l2!=NULL){
              int yu = 0;
              int x = l1->val;
              int y = l2->val;
            if((x+y+yu)>9){
                l->val = (x+y+yu)-10;
                l=l->next;
                yu = 0;
                l1 = l1->next;
                l2 = l2->next;
            }
            else{
                l->val = x+y;
                l=l->next;
                l1 = l1->next;
                l2 = l2->next;
            }  
            }
            return l;
        }
        
    }
};

