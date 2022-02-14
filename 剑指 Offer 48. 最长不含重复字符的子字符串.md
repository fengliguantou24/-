![image-20220213212913705](C:\Users\24\AppData\Roaming\Typora\typora-user-images\image-20220213212913705.png)

```c
const int N=40000;

class Solution {
public:
    int lengthOfLongestSubstring(string s) {
    int a[N]={0};
    int res=0;
    int j=0;
    for(int i=0;i<s.size();i++){
        a[s[i]]++;
        while(a[s[i]]>1){
            a[s[j]]--;
            j++;
        }
        res=max(res,i-j+1);
        
    }
    return res;
    }
};