# Tic-tac-toe-game
#include<stdio.h>
char box[11]={'0','1','2','3','4','5','6','7','8','9'};
void create_board(){
    printf("   |   |   \n");
    printf(" %c | %c | %c \n",box[1],box[2],box[3]);
    printf("___|___|___\n");
    printf("   |   |   \n");
    printf(" %c | %c | %c \n",box[4],box[5],box[6]);
    printf("___|___|___\n");
    printf("   |   |   \n");
    printf(" %c | %c | %c \n",box[7],box[8],box[9]);
    printf("   |   |   \n");
}

void marking_board(int choice,char mark){
    printf("The choice entered is :%d\n",choice);
    if(choice==1 && box[1]=='1')
    box[1]=mark;
    else if(choice==2 && box[2]=='2')
    box[2]=mark;
    else if(choice==3 && box[3]=='3')
    box[3]=mark;
    else if(choice==4 && box[4]=='4')
    box[4]=mark;
    else if(choice==5 && box[5]=='5')
    box[5]=mark;
    else if(choice==6 && box[6]=='6')
    box[6]=mark;
    else if(choice==7 && box[7]=='7')
    box[7]=mark;
    else if(choice==8 && box[8]=='8')
    box[8]=mark;
    else if(choice==9 && box[9]=='9')
    box[9]=mark;
    else
    printf("Invalid choice\n");


}

int check_winner(){
if(box[1]==box[2] && box[2]==box[3])
return 1;
else if(box[1]==box[4] && box[4]==box[7])
return 1;
else if(box[1]==box[5] && box[5]==box[9])
return 1;
else if(box[2]==box[5] && box[5]==box[8])
return 1;
else if(box[3]==box[6] && box[6]==box[9])
return 1;
else if(box[4]==box[5] && box[5]==box[6])
return 1;
else if(box[7]==box[8] && box[8]==box[9])
return 1;
else if(box[3]==box[5] && box[5]==box[7])
return 1;
else if(box[1]!='1'&&box[2]!='2'&&box[3]!='3'&& box[4]!='4'&&box[5]!='5'&&box[6]!='6'&&box[7]!='7'&&box[8]!='8'&&box[9]!='9')
return 0;
else
return -1;
}

int main(){
    int player=1;
    int choice,i;
    char mark;
    do{
    create_board();
    printf("Choose X for player(1)\t&\tO for player(2).\n");
    player=(player%2)?1:2;
     printf("Player%d...Enter the position:\n",player);
     scanf("%d",&choice);
     mark=(player==1)?'X':'O';
     marking_board(choice,mark);
     i=check_winner();
     player++;
    }while(i==-1);

    create_board();
    if(i==1)
    printf("Player%d u won the game.",--player);
    else
    printf("Match draw");
    
}
