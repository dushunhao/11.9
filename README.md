#define _CRT_SECURE_NO_WARNINGS 1

#include<stdio.h>

int my_strlen(char*str)

{

	int count = 0;

	while (*str != '\0')

	{

		count++;

		str++;

	}

	return count;

}


int my_strlen(char*str)

{

	if (*str != '\0')

		return 1 + my_strlen(str + 1);

	else

		return 0;

}


int main()

{

	char arr[] = "bit";

	//['b']['i']['t']['\0']

	//模拟一个strlen函数

	printf("%d\n", my_strlen(arr));

	return 0;

}


int main()

{

	int x, y = 98;

	for (x = 0; x <= 98; x++)

	{

		if (2 * x + 4 * y == 386)

		{

			printf("共有 %d 只鸡，%d 只兔\n", x, y);

		}

		y--;

	}

	return 0;

}  


int main()

{

	int x, y, z, i = 1;

	for (x = 0; x <= 20; x++)

	{

		for (y = 0; y <= 34; y++)

		{

			for (z = 0; z <= 100; z = z + 3)

			{

				if (5 * x + 3 * y + z / 3 == 100 && x + y + z == 100)

                                {

					printf("第%d种情况:公鸡%d只,母鸡%d只，小鸡%d只\n",i, x, y, z);

					i++;

				}
			}
		}
	}
	printf("\n共有%i种买法\n", i - 1);

	return 0;

}

//递归与迭代（循环）

int main()

{

	int n = 0;

	scanf("%d", &n);

	int i = 0;

	int ret = 1;

	for (i = 1; i <= n; i++)

	{

		ret = ret * i;

	}

	printf("%d\n", ret);

	return 0;

}

int Fac(int n)

{

	if (n <= 1)

		return 1;

	else

		return n * Fac(n - 1);

}


int main()

{

	int n = 0;

	scanf("%d", &n);


	int ret = Fac(n);


	printf("%d\n", ret);

	return 0;

}


//求第n个斐波那契数

//1.

//此方法效率太低，重复大量计算

int count=0;

int Fib(int n)

{

  //统计第3个斐波那契数的次数

  if (n == 3)

      count++;

	if (n <= 2)

		return 1;

	else

		return Fib(n - 1) + Fib(n - 2);

}

int main()

{

	int n = 0;

	scanf("%d", &n);

	int ret = Fib(n);


	printf("%d\n", ret);

  printf("count=%d\n", count);

	return 0;

}

//2.循环
int Fib(int n)

{

	int a = 1;

	int b = 1;

	int c = 1;

	while (n > 2) 

	{

		c = a + b;

		a = b;

		b = c;

		n--;

	}

	return c;

}


int main()

{

	int n = 0;

	scanf("%d", &n);

	int ret = Fib(n);

	printf("%d\n", ret);

	return 0;

}


int main()

{

	int i = 0;

	int count = 0;

	for (i = 1; i <= 100; i++)

	{

		if (i % 10 == 9)

			count++;

		if (i / 10 == 9)

			count++;

	}

	printf("%d\n", count);

	return 0;

}


//计算1/1-1/2+1/3-1/4+1/5 --- 1/99-1/100 的值，打印结果

int main()

{

	int i = 0;

	double sum = 0;

	for (i = 1; i <= 100; i++)

	{

		if (i % 2 == 0)

			sum -= 1.0 / i;

		else

			sum += 1.0 / i;

	}

	printf("%lf\n", sum);

	return 0;

}

int main()

{

	int i = 0;

	double sum = 0;

	int flag = 1;

	for (i = 1; i <= 100; i++)

	{

		sum += flag * 1.0 / i;

		flag = -flag;

	}

	printf("%lf\n", sum);

	return 0;

}

//求10个整数中最大值

int main()

{

	int arr[10] = { 1,2,3,4,5,6,7,8,9,10 };

	int max = arr[0];

	int i = 0;

	for (i = 1; i <= 10; i++)

	{

		if (arr[i] > max)

		{

			max = arr[i];

		}

	}

	printf("%d\n", max);


	return 0;

}

//屏幕上输出乘法口诀表
int main()

{

	int i = 1;

	//行数

	for (i = 1; i <= 9; i++)

	{

		//打印一行

		int j = 0;

		for (j = 1; j <= i; j++)

		{

			printf("%d*%d=%-2d ", i, j, i*j);

		}

		printf("\n");

	}

	return 0;

}

//递归：函数自己调用自己

void print(unsigned int n)

{

	if (n > 9)

	{

		print(n / 10);

	}

	printf("%d ", n % 10);

}

int main()

{

	unsigned int num = 0;

	scanf("%u", &num);//1234

	//递归的形式

	print(num);//打印参数部分数字的每一位

	return 0;

}

//写递归的时候（防止栈溢出）

//1.不能死递归，都有跳出条件，每次递归逼近跳出条件

//2.递归层次不能太深


void print_table(int n)

{

	int i = 0;

	for (i = 1; i <= n; i++)

	{

		int j = 0;

		for (j = 1; j <= i; j++)

		{

			printf("%d*%d=%-2d ",i, j, i*j);

		}

		printf("\n");

	}

}

int main()

{

	int n = 0;

	scanf("%d", &n);//9

	print_table(n);

	return 0;

}


int my_strlen(char*str)

{

	int count = 0;

	while (*str != '\0')

	{

		count++;

		str++;

	}

	return count;

}

void reverse_string(char* str)

{

	int left = 0;

	int right = my_strlen(str) - 1;

	while(left<right)

	{

		char tmp = str[left];

		str[left] = str[right];


		str[right] = tmp;

		left++;

		right--;

	}

}

int main()

{

	char arr[] = "abcdef";

	reverse_string(arr);

	printf("%s\n", arr);

	return 0;

}

int my_strlen(char*str)

{

	int count = 0;

	while (*str != '\0')

	{

		count++;

		str++;

	}

	return count;

}

void reverse_string(char*str)

{

	char tmp = *str;

	int len = my_strlen(str);

	*str = *(str + len - 1);

	*(str + len - 1) = '\0';

	if (my_strlen(str+1)>=2)

	{

		reverse_string(str + 1);

	}

		*(str + len - 1) = tmp;
	
}

int main()

{

	char arr[] = "abcdef";

	reverse_string(arr);

	printf("%s\n", arr);

	return 0;

}
