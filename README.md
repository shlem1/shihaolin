#include"stdio.h"
#include<conio.h>
#include <windows.h>
#include<stdlib.h>
int main()
{
	char A;
	int i;
  COORD pos;
  pos.X=0;
  pos.Y=0;
  char zbc[9][10]={"***####*",
	  "#*****#*",
	  "**###****", 
	  "********#",
	  "****####*",
	  "#*#*****#",
	  "******##Z",
	  "#*#******", 
	  "*****#**#"};//z是终点，‘*’可行，‘#’不可行
   while(1)
   {
      system("cls");
		  for(i=0;i<9;i++)
			  printf("%s\n",zbc[i]);
		 SetConsoleCursorPosition(GetStdHandle(STD_OUTPUT_HANDLE),pos);
		  printf("Y");
		  A=getch();
		   if (zbc[pos.Y][pos.X]=='Z')
		   {printf("抵达终点\n");break;}
		  switch(A)
		{  case'w': pos.Y--;
		      if(pos.Y<1) pos.Y=0;
			  if (zbc[pos.Y][pos.X]=='#')pos.Y++;
			  break;
		    case 's':pos.Y++;
		      if(pos.Y>10) pos.Y=10;
            if (zbc[pos.Y][pos.X]=='#')pos.Y--;
                break;
			case'a': pos.X--;
		      if(pos.X<1) pos.X=0;
			     if (zbc[pos.Y][pos.X]=='#')pos.X++;
             break; 
			case'd':pos.X++;
		      if(pos.X>=10) pos.X=10;
			  if (zbc[pos.Y][pos.X]=='#')pos.X--;
		      break;
   }}
  return 0;

}
