#include<stdio.h>
int main()
{
    char ttt[9]={' ',' ',' ',' ',' ',' ',' ',' ',' '};
    char move='x', em=' ';
    int pos;

    for(int i=1;i<=9;i++)
    {
        printf("enter your move ");
        scanf("%d",&pos);

       
        if(pos < 0 || pos > 8)
        {
            printf("Invalid position! Use 0-8.\n");
            i--; 
            continue;
        }

        if(ttt[pos] != em)
        {
            printf("already taken\n");
            i--;                     
            continue;
        }

        ttt[pos] = move;            
       
        printf("%c|%c|%c\n", ttt[0], ttt[1], ttt[2]);
        printf("-+-+-\n");
        printf("%c|%c|%c\n", ttt[3], ttt[4], ttt[5]);
        printf("-+-+-\n");
        printf("%c|%c|%c\n", ttt[6], ttt[7], ttt[8]);

       
        if(ttt[0]==move && ttt[1]==move && ttt[2]==move) break;
        if(ttt[3]==move && ttt[4]==move && ttt[5]==move) break;
        if(ttt[6]==move && ttt[7]==move && ttt[8]==move) break;

        if(ttt[0]==move && ttt[3]==move && ttt[6]==move) break;
        if(ttt[1]==move && ttt[4]==move && ttt[7]==move) break;
        if(ttt[2]==move && ttt[5]==move && ttt[8]==move) break;

        if(ttt[0]==move && ttt[4]==move && ttt[8]==move) break;
        if(ttt[2]==move && ttt[4]==move && ttt[6]==move) break;

       
        if(move=='x') move='o';
        else move='x';
    }

   
    if(
        (ttt[0]==move && ttt[1]==move && ttt[2]==move) ||
        (ttt[3]==move && ttt[4]==move && ttt[5]==move) ||
        (ttt[6]==move && ttt[7]==move && ttt[8]==move) ||
        (ttt[0]==move && ttt[3]==move && ttt[6]==move) ||
        (ttt[1]==move && ttt[4]==move && ttt[7]==move) ||
        (ttt[2]==move && ttt[5]==move && ttt[8]==move) ||
        (ttt[0]==move && ttt[4]==move && ttt[8]==move) ||
        (ttt[2]==move && ttt[4]==move && ttt[6]==move)
      )
    {
        printf("%c wins, game over\n", move);
    }
    else
    {
        printf("It's a tie!\n");      
    }

    return 0;
}
