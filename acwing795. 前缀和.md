![image-20220204223823374](C:\Users\24\AppData\Roaming\Typora\typora-user-images\image-20220204223823374.png)

```c
#include<stdio.h>

const int N=100001;



int a[N];
int s[N];
int main(){
int n,m,l,r;
scanf("%d %d",&n,&m);
for(int i=1;i<=n;i++){
    scanf("%d",&a[i]);
    s[i]=s[i-1]+a[i];
}

while(m--){
    scanf("%d %d",&l,&r);
    printf("%d\n",s[r]-s[l-1]);
}

}
```

