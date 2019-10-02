#include <stdio.h>
#include <stdlib.h>
int fncount(int,int,int);
int table,m;
void displaymonth(int);
void displayyear(int);
void display(int);
void display_table(int,int,int,int,int);
int main()
{
    FILE *p;
    p=fopen("india_days.txt","w");
    fclose(p);
    int n,y;
    printf("press 1 to see the day and detials \npress 2 to exit\n");
    while(1)
    {
        m=0;
        table=0;
        printf("\n\n enter the number \n");
        scanf("%d",&n);
    if(n==1){
    int day;
    int time,date,year,month;
    printf("\nenter the date : ");
    scanf("%d",&date);
    printf("\nenter the month : ");
    scanf("%d",&month);
    printf("\nenter the year : ");
    scanf("%d",&year);
    time=fncount(date,month,year);
        day=(time%7);
    display_table(table,date,month,year,day);

    printf("\n\nyour selected date details \n");
    printf(" __________________________\n");
    printf("| DATE  | %2d              |\n",date);
    printf("|_______|_________________|\n");
    printf("| DAY   ");
    display(day);
    printf("|_______|_________________|\n");
    printf("| MONTH | %2d  ",month);displaymonth(month);
    printf("\n|_______|_____|___________|\n");
    printf("|YEAR   |%3d ",year);displayyear(year);
    printf("\n|_______|_____|___________|\n\n");


    }
    else
    {
        exit(0);
    }
    }
    return 0;

}
int fncount(int fdate,int fmonth,int fyear)
{
    int count=0;
    long int i;
    for(i=2000;i<fyear;i++)
    {
        if(i%4==0)
        {
            count=count+366;
            table=count;
        }
        else
        {
            count=count+365;
            table=count;
        }

    }
    if(fyear%4==0)
    {
        for(i=1;i<fmonth;i++)
        {
            if(i==1||i==3||i==5||i==7||i==8||i==10||i==12)
            {
                count=count+31;
                table=count;
            }
            else if(i==2)
            {
                count=count+29;
                table=count;
            }
            else
            {
                count=count+30;
                table=count;
            }
        }
     }
     else
    {
        for(i=1;i<fmonth;i++)
        {
            if(i==1||i==3||i==5||i==7||i==8||i==10||i==12)
            {
                count=count+31;
                table=count;
            }
            else if(i==2)
            {
                count=count+28;
                table=count;
            }
            else
            {
                count=count+30;
                table=count;
            }
        }
     }
     count=count+fdate;
     return count;
}
void display(int day)
{
    if(day==1)
    {
        printf("| SATURDAY        |\n");
    }
    else if(day==2)
    {
        printf("| SUNDAY          |\n");
    }
    else if(day==3)
    {
        printf("| MONDAY          |\n");
    }
    else if(day==4)
    {
        printf("| TUESDAY         |\n");
    }
    else if(day==5)
    {
        printf("|  WEDNESDAY      |\n");
    }
    else if(day==6)
    {
        printf("| THURSDAY        |\n");
    }
    else if(day==0)
    {
        printf("| FRIDAY          |\n");
    }
    return;
}
void display_table(int ftable,int fdate,int fmonth,int fyear,int fday)
{
    int i=fmonth,j,k,x,y;
    int ftb=(ftable+6)%7;
    for(k=0;k<49;k++)
    {
        printf("_");
    }
    printf("\n| SUN  |  MON | TUE  | WED  | THR  | FRI  | SAT  |\n");
    printf("|______|______|______|______|______|______|______|");
    printf("\n");
    if(fyear%4==0)
    {

        if(i==1||i==3||i==5||i==7||i==8||i==10||i==12)
        {
            for(k=1;k<=6;k++)
            {
                if(m<31){
                printf("|");
                for(j=1;j<=7;j++)
                {
                    if(m<31){
                    if(k==1&&j>ftb)
                    {
                        m++;
                        if(fdate==m)
                        {
                            printf(" (%2d) |",m);
                        }
                        else
                        {
                            printf("  %2d  |",m);
                        }
                    }
                    else if(k==1&&j<=ftb)
                    {
                        printf("      |");
                    }
                    else if(k>1)
                    {
                        m++;
                        if(fdate==m)
                        {
                            printf(" (%2d) |",m);
                        }
                        else
                        {
                            printf("  %2d  |",m);
                        }
                    }

                }
                }
                printf("\n");

                for(x=0;x<=49;x++)
                {
                    if(x==0||x==7||x==14||x==21||x==28||x==35||x==42||x==49)
                    {
                        printf("|");
                    }
                    else
                    {
                        printf("_");
                    }
                }
                printf("\n");
            }
        }
        }
        else if(i==2)
        {

            for(k=1;k<6;k++)
            {
                if(m<29){
                printf("|");
                for(j=1;j<=7;j++)
                {
                    if(m<29){
                    if(k==1&&j>ftb)
                    {
                        m++;
                        if(fdate==m)
                        {
                            printf(" (%2d) |",m);
                        }
                        else
                        {
                            printf("  %2d  |",m);
                        }
                    }
                    else if(k==1&&j<=ftb)
                    {
                        printf("      |");
                    }
                    else if(k>1)
                    {
                        m++;
                        if(fdate==m)
                        {
                            printf(" (%2d) |",m);
                        }
                        else
                        {
                            printf("  %2d  |",m);
                        }
                    }
                    }
                    else{
                    }
                }
                printf("\n");
                for(x=0;x<=49;x++)
                {
                    if(x==0||x==7||x==14||x==21||x==28||x==35||x==42||x==49)
                    {
                        printf("|");
                    }
                    else
                    {
                        printf("_");
                    }
                }
                printf("\n");
                }
            }
        }
        else{
    for(k=1;k<=6;k++)
            {
                if(m<30){
                printf("|");
                for(j=1;j<=7;j++)
                {
                    if(m<30){
                    if(k==1&&j>ftb)
                    {
                        m++;
                        if(fdate==m)
                        {
                            printf(" (%2d) |",m);
                        }
                        else
                        {
                            printf("  %2d  |",m);
                        }
                    }
                    else if(k==1&&j<=ftb)
                    {
                        printf("      |");
                    }
                    else if(k>1)
                    {
                        m++;
                        if(fdate==m)
                        {
                            printf(" (%2d) |",m);
                        }
                        else
                        {
                            printf("  %2d  |",m);
                        }
                    }

                }
                }
                printf("\n");

                for(x=0;x<=49;x++)
                {
                    if(x==0||x==7||x==14||x==21||x==28||x==35||x==42||x==49)
                    {
                        printf("|");
                    }
                    else
                    {
                        printf("_");
                    }
                }
                printf("\n");
            }
        }
        }
    }
    else
        {

        if(i==1||i==3||i==5||i==7||i==8||i==10||i==12)
        {
            for(k=1;k<=6;k++)
            {
                if(m<31){
                printf("|");
                for(j=1;j<=7;j++)
                {
                    if(m<31){
                    if(k==1&&j>ftb)
                    {
                        m++;
                        if(fdate==m)
                        {
                            printf(" (%2d) |",m);
                        }
                        else
                        {
                            printf("  %2d  |",m);
                        }
                    }
                    else if(k==1&&j<=ftb)
                    {
                        printf("      |");
                    }
                    else if(k>1)
                    {
                        m++;
                        if(fdate==m)
                        {
                            printf(" (%2d) |",m);
                        }
                        else
                        {
                            printf("  %2d  |",m);
                        }
                    }

                }
                }
                printf("\n");

                for(x=0;x<=49;x++)
                {
                    if(x==0||x==7||x==14||x==21||x==28||x==35||x==42||x==49)
                    {
                        printf("|");
                    }
                    else
                    {
                        printf("_");
                    }
                }
                printf("\n");
            }
        }
        }
        else if(i==2)
        {

            for(k=1;k<6;k++)
            {
                if(m<28){
                printf("|");
                for(j=1;j<=7;j++)
                {
                    if(m<28){
                    if(k==1&&j>ftb)
                    {
                        m++;
                        if(fdate==m)
                        {
                            printf(" (%2d) |",m);
                        }
                        else
                        {
                            printf("  %2d  |",m);
                        }
                    }
                    else if(k==1&&j<=ftb)
                    {
                        printf("      |");
                    }
                    else if(k>1)
                    {
                        m++;
                        if(fdate==m)
                        {
                            printf(" (%2d) |",m);
                        }
                        else
                        {
                            printf("  %2d  |",m);
                        }
                    }
                    }
                    else{
                    }
                }
                printf("\n");
                for(x=0;x<=49;x++)
                {
                    if(x==0||x==7||x==14||x==21||x==28||x==35||x==42||x==49)
                    {
                        printf("|");
                    }
                    else
                    {
                        printf("_");
                    }
                }
                printf("\n");
                }
            }
        }
        else{
    for(k=1;k<=6;k++)
            {
                if(m<30){
                printf("|");
                for(j=1;j<=7;j++)
                {
                    if(m<30){
                    if(k==1&&j>ftb)
                    {
                        m++;
                        if(fdate==m)
                        {
                            printf(" (%2d) |",m);
                        }
                        else
                        {
                            printf("  %2d  |",m);
                        }
                    }
                    else if(k==1&&j<=ftb)
                    {
                        printf("      |");
                    }
                    else if(k>1)
                    {
                        m++;
                        if(fdate==m)
                        {
                            printf(" (%2d) |",m);
                        }
                        else
                        {
                            printf("  %2d  |",m);
                        }
                    }

                }
                }
                printf("\n");

                for(x=0;x<=49;x++)
                {
                    if(x==0||x==7||x==14||x==21||x==28||x==35||x==42||x==49)
                    {
                        printf("|");
                    }
                    else
                    {
                        printf("_");
                    }
                }
                printf("\n");
            }
        }
        }
    }

    return;
}
void displaymonth(int fmonth)
{
    int day=fmonth;
    if(day==1)
    {
        printf("| JANUARY   |");
    }
    else if(day==2)
    {
        printf("| FEBRUARY  |");
    }
    else if(day==3)
    {
        printf("| MARCH     |");
    }
    else if(day==4)
    {
        printf("| APRIAL    |");
    }
    else if(day==5)
    {
        printf("|  MAY      |");
    }
    else if(day==6)
    {
        printf("| JUNE      |");
    }
    else if(day==7)
    {
        printf("| JULY      |");
    }
    else if(day==8)
    {
        printf("| AUGUST    |");
    }
    else if(day==9)
    {
        printf("| SEPTEMBER |");
    }
    else if(day==10)
    {
        printf("| OCTOBER   |");
    }
    else if(day==11)
    {
        printf("| NOVEMBER  |");
    }
    else if(day==12)
    {
        printf("| DECEMBER  |");
    }
    return 0;
}
void displayyear(int year)
{
    if(year%4==0)
    {
        printf("|  LEAF YEAR|");
    }
    else
    {
        printf("|NOT-LEAF-Yr|");
    }
    return 0;
}
