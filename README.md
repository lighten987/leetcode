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
class Solution{  
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
//修改后代码 AC      
class Solution {  
public:  
    ListNode* addTwoNumbers(ListNode* l1, ListNode* l2) {  
        ListNode* l = NULL,**t = &l;  
        int yu = 0,x = 0, y = 0,sum = 0;  
            while(l1!=NULL || l2!=NULL){  
               if(l1 != NULL)x = l1->val;else x = 0;  
               if(l2 != NULL)y = l2->val;else y = 0;  
               sum = x+y+yu;  
                ListNode *node = new ListNode(sum%10);  
                *t = node;  
                t=(&node->next);  
                yu = sum/10;  
                if(l1 != NULL)l1 = l1->next;  
                if(l2 != NULL)l2 = l2->next;  
            }  
        if(yu){  
           ListNode *node = new ListNode(yu%10);   
           *t = node;  
        }  
            return l;     
    }  
};  
//**注意：**链表数字可能出现不等长情况，用等长情况写的代码容易出现指向空指针，所以需要判断是否是尾链表，如果是尾链表还要注意以后的取值都为零  


