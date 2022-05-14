#include<stdio.h>
#include<string.h>

struct sut
{
	char nation[100];//国家
	int goldNumber;  //金牌数
	int silverNumber;//银牌数
	int bronzeNumber;//铜牌数
	int sum;         //总数
};
int main()
{
	struct sut a[100] = {'\0'};
	struct sut *pa = a;
	char str[9][100] = { '\0' };
	int i;
	FILE *fp = fopen("D:\\VS2015\\file.txt", "r");
	if (fp == NULL)
	{
		printf("Error\n");
		return 0;
	}
	
	while (fscanf(fp, "%s %d %d %d %d", pa->nation, &pa->goldNumber, &pa->silverNumber, &pa->bronzeNumber, &pa->sum) != EOF)
	{
		printf("%-12s%-8d%-8d%-8d%-8d\n", pa->nation, pa->goldNumber, pa->silverNumber, pa->bronzeNumber, pa->sum);
		pa++;
	}
	fclose(fp);
	
	struct sut t;
	for (i = 0; i < 8; i++)
	{
		for (int j = 0; j < 7; j++)
		{
			if (a[j].sum > a[j + 1].sum)
			{
				t = a[j];
				a[j] = a[j + 1];
				a[j + 1] = t;
			}
		}
	}

	
	printf("\n\n");
	FILE *max = fopen("D:\\VS2015\\now1.txt", "w");    //文件指针（奖牌数最多的国家）
	FILE *min = fopen("D:\\VS2015\\now2.txt", "w");    //文件指针（奖牌数最少的国家）
	fprintf(max, "%-12s%-8d%-8d%-8d%-8d\n", a[7].nation, a[7].goldNumber, a[7].silverNumber, a[7].bronzeNumber, a[7].sum); //将奖牌数最多的国家写到文件now1.txt中
	fprintf(min, "%-12s%-8d%-8d%-8d%-8d\n", a[0].nation, a[0].goldNumber, a[0].silverNumber, a[0].bronzeNumber, a[0].sum); //将奖牌数最少的国家写到文件now2.txt中
	fclose(max); //关闭文件
	fclose(min);
	

	printf("---奖牌数最多的国家是:%-12s 金牌:%-8d 银牌:%-8d 铜牌:%-8d 奖牌数:%-8d---\n"
		, a[7].nation, a[7].goldNumber, a[7].silverNumber, a[7].bronzeNumber, a[7].sum);  //打印奖牌数最多的国家到屏幕
	printf("---奖牌数最少的国家是:%-12s 金牌:%-8d 银牌:%-8d 铜牌:%-8d 奖牌数:%-8d---\n"   //打印奖牌数最少的国家到屏幕
		, a[0].nation, a[0].goldNumber, a[0].silverNumber, a[0].bronzeNumber, a[0].sum);


	for (i = 0; i < 8; i++)
	{
		for (int j = 0; j < 7; j++)
		{
			if (a[j].goldNumber > a[j + 1].goldNumber)
			{
				t = a[j];
				a[j] = a[j + 1];
				a[j + 1] = t;
			}
		}
	}

	FILE *wfp = fopen("D:\\VS2015\\file_sorted.txt", "w");  //按照金牌奖牌数量进行升序排序并输出结果到 file_sorted.txt
	for (i = 0; i<8; i++)
	{
		fprintf(wfp, "%-12s%-8d%-8d%-8d%-8d\n", a[i].nation, a[i].goldNumber, a[i].silverNumber, a[i].bronzeNumber, a[i].sum);
	}
	fclose(wfp);//关闭文件
	return 0;
}
