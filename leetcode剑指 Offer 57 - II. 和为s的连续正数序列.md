![image-20220103222914150](C:\Users\24\AppData\Roaming\Typora\typora-user-images\image-20220103222914150.png)

```c
int** findContinuousSequence(int target, int* returnSize, int** returnColumnSizes){
int x=1;
int y=2;
//这时需要为二维数组申请空间
//还需要申请一个数组用来装连续数组的个数，每一个位置都代表了当前的连续的数据个数
int mid=target/2;
int **ras=(int**)malloc(sizeof(int*)*mid);//为二维数组申请空间
int *col=(int*)malloc(sizeof(int)*mid);
int sum=x+y;
int size=0;

int m=0;
    while(x<=mid){
        if(sum<target){//这时说明需要加上范围
            y++;
            sum+=y;
        }

        else if(sum>target){//这时说明需要减小范围
            sum-=x;
            x++;
        }
        else{//这时说明sum==target，说明刚好找到一组了。
    col[m]=y-x+1;//这里计算的是这个数组里面的元素个数
    ras[m]=(int*)malloc(sizeof(int)*col[m]);
    //现在需要将这些个数据装到这个二维数组中去
    for(int i=0;i<col[m];i++){
        ras[m][i]=x+i; 
    }
    m++;
    sum-=x;
    x++;
        }
    }  
    *returnSize=m;
    *returnColumnSizes=col;
    return ras;
}
```

