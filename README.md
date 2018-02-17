#include<stdio.h>
#include <stdlib.h>

int main()
{
    char S1[100],S2[100],f[]="FLAMES";
    int i,j,k=0,count=-1;
    scanf("%s %s",S1,S2);
    for(i=0;i<strlen(S1);i++)
    {
        for(j=0;j<strlen(S2);j++)
        {
            if(tolower(S1[i])==tolower(S2[j]))
            {
                S1[i]=S2[j]='*';
                break;
            }
        }
    }
    for(i=0;i<strlen(S1);i++)
    {
        if(S1[i]!='*')
            k++;
    }
    for(j=0;j<strlen(S2);j++)
    {
        if(S2[j]!='*')
            k++;
    }
    for(i=0;i<strlen(f)-1;i++)
    {
        for(j=0;j<k;j++)
        {
            count++;
            while(f[count%strlen(f)]=='*')
                count++;
        }
        f[count%strlen(f)]='*';
    }
    for(i=0;i<strlen(f);i++)
        if(f[i]!='*')
            break;
    if(i==0)
        printf("FRIENDS");
    else if(i==1)
        printf("LOVER");
    else if(i==2)
        printf("AFFECTION");
    else if(i==3)
        printf("MARRIAGE");
    else if(i==4)
        printf("ENEMY");
    else
	printf("SIBLING");
	

}
