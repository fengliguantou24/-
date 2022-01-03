![image-20220103094235611](C:\Users\24\AppData\Roaming\Typora\typora-user-images\image-20220103094235611.png)





```c

int tribonacci(int n){
    int t[100];
    t[0]=0;
    t[1]=1;
    t[2]=1;
    for(int i=3;i<=n;i++)
    t[i]=t[i-1]+t[i-2]+t[i-3];

    return t[n];
}
```