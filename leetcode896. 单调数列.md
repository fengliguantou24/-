![image-20220103223014088](C:\Users\24\AppData\Roaming\Typora\typora-user-images\image-20220103223014088.png)

```c
bool isMonotonic(int* nums, int numsSize) {
    bool temp1 = true, temp2 = true;
    
    for (int i = 0; i < numsSize - 1; i++) {
        if (nums[i] > nums[i + 1]) {
            temp1= false;
        }
        if (nums[i] < nums[i + 1]) {
            temp2 = false;
        }
    }
    return temp1 || temp2;
}