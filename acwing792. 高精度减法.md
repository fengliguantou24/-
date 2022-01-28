![image-20220128205302185](C:\Users\24\AppData\Roaming\Typora\typora-user-images\image-20220128205302185.png)

```c
#include<iostream>
using namespace std;
#include<vector>
#include<string>


int cmp(string a,string b){
    if(a.size()==b.size()){
        for(int i=0;i<a.size();i++)
        if(a[i]!=b[i])
        return a[i]>=b[i];
    }
    return a.size()>=b.size();
}
vector<int> sub(vector<int>&v1,vector<int>&v2){
    //大的数字减去小的数字，所以先需要判断哪个数字大
    //这里默认是v1里存储的数字比较大了
    int t=0;
    vector<int> c;
    for(int i=0;i<v1.size();i++){
        t+=v1[i];
        if(i<v2.size())
        t-=v2[i];
        c.push_back((t+10)%10);
        if(t<0)
        t=-1;
        else
        t=0;
    }
    //需要去掉前导0
    while(c.size()>1&&c.back()==0){
        
        c.pop_back();
    }
    return c;
}



int main(){
    vector<int> v1,v2;
    string a,b;
    cin>>a>>b;
    
    for(int i=a.size()-1;i>=0;i--){
        v1.push_back(a[i]-'0');
    }
     for(int i=b.size()-1;i>=0;i--){
        v2.push_back(b[i]-'0');
    }
    
    
    if(cmp(a,b)){
        auto c=sub(v1,v2);
       for(int i=c.size()-1;i>=0;i--)
        cout<<c[i];
    }
    
    else{
        auto c=sub(v2,v1);
        cout<<'-';
        for(int i=c.size()-1;i>=0;i--)
        cout<<c[i];
           
    }
 
}
```

