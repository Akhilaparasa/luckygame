# luckygame
#include<stdio.h>
#include<stdlib.h>
#include<time.h>                             // to include srand(time(0)) into the code.
int main()
{
 char name[100],ch;
int n,c,j,k,b[4],i;
int num[10],count;
srand(time(0));                               // to give different random numbers each time executed.
printf("---------- Welcome to luck game -----------\n");
printf("Hello... I am your Partner in this game...");
printf("Can i know your sweet name please\n");
scanf("%s",name);
printf("%s choose your choice: \n1)How to enjoy this game. \t 2)Play \t 3)How are scores calculated?\n",name);
scanf("%d",&n);
if(n==1)
{
    printf("------------How to enjoy this game-------------\n");
    printf("1)Enter any 4 different numbers from 1 to 9.");
    printf("\n2)I will generate some random number which will be displayed as well.");
    printf("\n3)The last 4 number of my generated numbers and the numbers you have entered will be checked");
    printf("\n4)I will calculate how many numbers are matching and it will be displayed");
    printf("\n5)Scores will be awarded as per the matching numbers");
    printf("\n6)WARNING: Do not use enter.");
    printf("\n6)Once you have seen the instruction.Exit and start from the begining");
}
else if(n==2)
{
     printf("enter any 4 different number between 1 and 9:");
     for(j=0;j<4;j++)
     {
         scanf("\t%d",&b[j]);
         printf("%d ",b[j]);
     }
     for(j=0;j<4;j++)
     {
         for(i=j+1;i<4;i++)
         {
             if(b[j]==b[i])
             {
                 c=1;
             }
             else
             {
                 c=0;
             }
         }
     }
     if(c==1)
     {
         printf("\nYour numbers are same.Print different numbers.\n");
     }
}
     if(c==0)
     {
     printf("\n");
    printf("Random numbers are: ");
    for(k=0;k<9;k++)
    {
        num[k]=rand()%10;                      // to print random numbers.
        printf("%d ",num[k]);
    }
   printf("\n");
   count=0;
    for(k=5;k<9;k++)
    {
        for(j=0;j<4;j++)
        {
           if(num[k]==b[j])                      // to check if the number entered and random numbers are same or not. 
          {
             count++;
             break; 
          }
        }
      }
     }
 else if(n==3)
 {
     printf("1)max score = 60 and min score = 20");
     printf("\n2)If you get 2 number matching,then you score=20");
     printf("\n3)If you get 3 numbers matching,your score=40");
     printf("\n4)If you get 4(max)numbers matching,your score=60");
     printf("\n5)Once you have read,exit and start from begining");
 }
 switch(count)                                                           // to print score and comment.
 {
     case 2:
          printf
          ("Not bad.Congratulations. %s have got 2 correct",name);
          printf("\n%s score = 20",name);
          break;
     case 3:
           printf("Very good.You are nice guesser. %s have got 3 correct",name);
           printf("\n%s score = 40",name);
           break;
     case 4:
          printf("Excellent.Nice guess dear. %s have got all correct",name);
          printf("\n%s score = 60",name);
          break;
     case 1:
         printf("Sorry %s\n",name);
         printf("Very poor.Do a better guess next time");
         break;
 }
}
