#include<stdio.h>
#include<string.h>
int main()
{
	int i, j,x=0;
	char str1[100],str2[20];
	puts("请输入英语句子");
	gets_s(str1);
	puts("请输入你想查询的单词");
	gets_s(str2);
	for (i = 0; i <strlen(str1); i++)
	{
			if (str1[i] == str2[0])
			{
				int k = 0;
				for (j = 0; j < strlen(str2); j++)
				{
					if (str1[i++] == str2[j])
					{
						k++;
					}
				}
				if (k == strlen(str2))  //判断是否是相同单词
				{
					x++;
				}
				i--;
			}
	}
	printf("相同的单词有：%d个\n", x);

	return 0;
}
