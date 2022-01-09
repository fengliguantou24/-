![image-20220109163708061](C:\Users\24\AppData\Roaming\Typora\typora-user-images\image-20220109163708061.png)





```c
int numSpecial(int** mat, int matSize, int* matColSize){



    int cout=0;
    int sum;
        for(int i=0;i<matSize;i++)
        {
             
            for(int j=0;j<*matColSize;j++)//
            {
                
                if(mat[i][j]==1)
                {
                    sum=0;
                    for(int k=0;k<*matColSize;k++){//先遍历行
                        sum+=mat[i][k];
                    }
                    for(int t=0;t<matSize;t++)
                    {
                         sum+=mat[t][j];
                    }
                   
                    if(sum==2)
                    cout++;
                    
                }
                
                
            }
        }

    return cout;



}
```

