//by Sushant Gaurav

#include<stdio.h>
#include<stdlib.h>

struct graph
{
    struct graph *edge[10];
    int info;
}node[10];


void display(int num)
{
    int i,j;
    printf("\n");

    for(i=1;i<=num;i++)
    {
        printf("Edges of node[%d] are: ",i);

        for(j=1;j<=num;j++)
        {
            if(node[i].edge[j]==NULL)
            continue;
            printf("(%d - %d) ",i,node[i].edge[j]->info);
        }
    printf("\n");
    }
}


void main()
{
    int i,j,N;
    char ch;

    printf("Enter number of vertex of graph : ");
    scanf("%d",&N);

    for(i=1;i<=N;i++)
    {
        node[i].info=i;

        for(j=1;j<=N;j++)
        {
            fflush(stdin);
            printf("Is there an edge from %d to %d ? (y/n): ",i,j);
            scanf("%c",&ch);

            if(ch=='y')
                node[i].edge[j]=&node[j];
            else
                node[i].edge[j]=NULL;
        }
    }
    display(N);
}
