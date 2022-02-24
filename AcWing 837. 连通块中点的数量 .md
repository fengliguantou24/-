![image-20220224215455677](C:\Users\24\AppData\Roaming\Typora\typora-user-images\image-20220224215455677.png)

![image-20220224215505582](C:\Users\24\AppData\Roaming\Typora\typora-user-images\image-20220224215505582.png)

```c
#include<iostream>
using namespace std;
#include<string>
const int N=110001;
int f[N],cnt[N];
int n,m;

int find(int x){
    if(f[x]!=x) f[x]=find(f[x]);
    return f[x];
}
int main(){
    scanf("%d%d",&n,&m);
    for(int i=1;i<=n;i++){
        f[i]=i;
        cnt[i]=1;
    }
    while(m--){
        int a,b;
        string op;
        cin>>op;
        if(op=="C"){
            scanf("%d%d",&a,&b);
             a=find(a);
             b=find(b);
            if(a!=b){
            f[a]=b;
            cnt[b]+=cnt[a];  
            }
        }   
        else if(op=="Q1"){
            scanf("%d%d",&a,&b);
            if(find(a)==find(b))
            printf("Yes\n");
            else
            printf("No\n");
        }
        else if(op=="Q2"){
            scanf("%d",&a);
            printf("%d\n",cnt[find(a)]);
        }
        
    }
}
```

