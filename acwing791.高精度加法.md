![image-20220126214328969](C:\Users\24\AppData\Roaming\Typora\typora-user-images\image-20220126214328969.png)

```c
#include<iostream>
#include<vector>

using namespace std;


vector<int> add(vector<int> &v1, vector<int> &v2)
{
     vector<int> c;
    
   
    int t = 0;
    for (int i = 0; i < v1.size()||i<v2.size(); i ++ )
    {
       if(i<v1.size())t+=v1[i];
       if(i<v2.size())t+=v2[i];
       c.push_back(t%10);
       t/=10;
    }
    
    if (t) c.push_back(1);
    return c;
}
int main(){
    string a,b;
    vector<int>v1,v2;
    
    cin>> a >> b;
    
    for(int i=a.size()-1;i>=0;i--) v1.push_back(a[i]-'0');
    for(int i=b.size()-1;i>=0;i--) v2.push_back(b[i]-'0');
       
 
    auto c=add(v1,v2);
    for(int i=c.size()-1;i>=0;i--)
        cout<<c[i];
    
    return 0;
    
}
```

