![image-20220102224442187](C:\Users\24\AppData\Roaming\Typora\typora-user-images\image-20220102224442187.png)





```c
bool isPowerOfTwo(int n){
	if (n == 0) {
		return false;
	}
	int x = (int)(log10(n)/log10(2));
	return (int)pow(2, x)== n;
}
```

