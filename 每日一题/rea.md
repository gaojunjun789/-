
# 7.整数反转
## 题目：
给你一个 32 位的有符号整数 x ，返回将 x 中的数字部分反转后的结果。

如果反转后整数超过 32 位的有符号整数的范围 [−231,  231 − 1] ，就返回 0。

假设环境不允许存储 64 位整数（有符号或无符号）。


示例 1：

输入：x = 123
输出：321
示例 2：

输入：x = -123
输出：-321
示例 3：

输入：x = 120
输出：21
示例 4：

输入：x = 0
输出：0
 

提示：

-231 <= x <= 231 - 1

来源：力扣（LeetCode）
链接：https://leetcode.cn/problems/reverse-integer
著作权归领扣网络所有。商业转载请联系官方授权，非商业转载请注明出处。
## 代码：
```C++
class Solution {
public:
    string findLongestWord(string s, vector<string>& dictionary) {
        string result;
        for(int i = 0; i < dictionary.size(); i++){
            if(sub(dictionary[i], s))
                if(dictionary[i].size() > result.size())
                    result = dictionary[i];
                else if(dictionary[i].size() == result.size())
                        if(dictionary[i] < result)
                            result = dictionary[i];
        }
        return result;
    }
private:
    bool sub(string su, string s){
        int i = 0;
        int j = 0;
        while(i < su.size() && j < s.size()){
            while(j < s.size() && s[j] != su[i])
                j++;
            if(j < s.size()){
                i++;
                j++;
            }
        }
        if(i >= su.size())
            return true;
        else    
            return false;
    }
};

```
## 思路：

## 代码小惊喜：
