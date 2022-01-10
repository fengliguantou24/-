![image-20220110101850434](C:\Users\24\AppData\Roaming\Typora\typora-user-images\image-20220110101850434.png)

```c
int* swapNumbers(int* numbers, int numbersSize, int* returnSize){

      *returnSize = numbersSize;
      *returnSize = numbersSize;
    numbers[0]=numbers[0]^numbers[1];
    numbers[1]=numbers[0]^numbers[1];
    numbers[0]=numbers[0]^numbers[1];
    return numbers;
}