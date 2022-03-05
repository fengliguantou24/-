![image-20220305221754111](C:\Users\24\AppData\Roaming\Typora\typora-user-images\image-20220305221754111.png)







```c
#include<iostream>
#include<cstring>
#include<cstdio>

using namespace std;
const int N=10;

int state[N];
int path[N];
int n;

void dfs(int u){
    if(u>n){
        for(int i=1;i<=n;i++)
        printf("%d ",path[i]);
        puts(" ");
        return ;
    }
    
    for(int i=1;i<=n;i++){
        if(!state[i]){
            state[i]=1;
            path[u]=i;
            dfs(u+1);
            state[i]=0;
        }
    }
}



int main(){
    cin>>n;
    dfs(1);
}

