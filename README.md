#include <windows.h>
#include <stdio.h>
#include <conio.h>
int main()
{
	char str[9][12] = 
		{"*#*********"
		,"***###*###*"
		,"###**#****#"
		,"*#**###**#*"
		,"***********"
		,"#####*##*##"
		,"**#*****#*E"
		,"***#*###**#"
		,"*#*********" };
	void gotoxy(int x, int y);
	int i, j;
	for (i = 0; i < 9; i++)
	{
		for (j = 0; j < 12; j++)
		{
			printf("%c", str[i][j]);
		}
		printf("\n");
	}
	int cax = 0, cay = 0;
	int move_x = 0, move_y = 0;
	gotoxy(0, 0);
	while (1)
	{

		char t = getch();
		switch (t)
		{
		case 72:move_y--; break;
		case 75:move_x--; break;
		case 77:move_x++; break;
		case 80:move_y++; break;
		}
		gotoxy(move_x, move_y);
		if (str[move_y][move_x] == '#')
		{
			switch (t)
			{
			case 72:move_y++; break;
			case 75:move_x++; break;
			case 77:move_x--; break;
			case 80:move_y--; break;
			}
			gotoxy(move_x, move_y);
		}
		else
		{
			if (move_x < 0)
				move_x++;
			if (move_x > 10)
				move_x--;
			if (move_y < 0)
				move_y++;
			if (move_y > 8)
				move_y--;
			gotoxy(move_x, move_y);
		}
		gotoxy(1, 9);
		{
			printf("x=%d,y=%d", move_x, move_y);
		}
		gotoxy(move_x, move_y);

		if (str[move_y][move_x] == 'E')
		{
			gotoxy(1, 10);
			printf("恭喜你成功走出小岛\n");break;
		}
	}

	return 0;
}
void gotoxy(int x, int y)
{
	COORD pos;
	pos.X = x;
	pos.Y = y;
	SetConsoleCursorPosition(GetStdHandle(STD_OUTPUT_HANDLE), pos);
}
