![image-20220130231237597](C:\Users\24\AppData\Roaming\Typora\typora-user-images\image-20220130231237597.png)







```C
#include<stdio.h>
#include<string.h>
const int N=100001;




int main(){
char a[N];
char b[N];
int arr[N]={0};
int brr[N]={0};
int crr[2*N]={0};
    scanf("%s",&a);
    scanf("%s",&b);
    int len1=strlen(a);
    int len2=strlen(b);
    
    for(int i=0;i<len1;i++){
        arr[i]=(a[len1-1-i]-'0');    
    }
    
    for(int i=0;i<len2;i++){
        brr[i]=(b[len2-1-i]-'0');    
    }//将数字插入逆序插入到数组中
   for(int i=0;i<len1;i++){
       for(int j=0;j<len2;j++){
           crr[i+j]+=arr[i]*brr[j];
           crr[i+j+1]+=crr[i+j]/10;
           crr[i+j]%=10;
       }
   }
   int len3=len2+len1;
   while(crr[len3-1]==0&&len3>1)
   len3--;
   for(int i=len3-1;i>=0;i--){
       printf("%d",crr[i]);
       
   }
   
   
}
```

