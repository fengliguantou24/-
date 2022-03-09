

![image-20220309200447357](C:\Users\24\AppData\Roaming\Typora\typora-user-images\image-20220309200447357.png)



```c
#include<iostream>
#include<cstring>
#include<cstdio>
using namespace std;
const int N=100010;

int n,m;
int q[N];

int main()
{
    scanf("%d%d",&n,&m);
    for(int i=0;i<n;i++)
    scanf("%d",&q[i]);
    while(m--){
        int x;
        scanf("%d",&x);
        
        int l=0;
        int r=n-1;
        while(l<r){
            int mid=(l+r)/2;
            if(q[mid]>=x)
            r=mid;
            else
            l=mid+1;
        }
        if(q[r]==x){
            cout<<r<<" ";
            l=r;
            r=n-1;
            while(l<r){
                int mid=(l+r+1)/2;
                if(q[mid]<=x)l=mid;
                else
                r=mid-1;
            }
            cout<<l<<endl;
        }
        else
        cout<<"-1"<<" "<<"-1"<<endl;
    }
    
}

```

