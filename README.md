# FCFS2-24jan
#include <stdio.h>
#include <string.h>
#include <math.h>
#include <stdlib.h>

int main() {
    int i,j,temp,p[4],a[4],b[4],w[4],sum=0;
    for(i=0;i<4;i++)
        scanf("%d%d%d",&p[i],&a[i],&b[i]);
    for(i=0;i<4;i++)
    {
        for(j=i+1;j<4;j++)
        {
        if(a[i]>a[j])
        {
            temp=a[i];
            a[i]=a[j];
            a[j]=temp;
            temp=b[i];
            b[i]=b[j];
            b[j]=temp;
            temp=p[i];
            p[i]=p[j];
            p[j]=temp;
            
        }
    }
    }
  
    for(int i=0;i<4;i++)
    {
        if(i==0)
        w[i]=0;
        else
        {
            sum=sum+b[i-1];
            w[i]=sum-a[i];
        
        }
    }
    for(int i=0;i<4;i++)
    {
        for(int j=0;j<4-1-i;j++)
        {
            if(p[j]>p[j+1])
            {
                int temp=p[j];
                p[j]=p[j+1];
                p[j+1]=temp;
                int temp1=w[j];
                w[j]=w[j+1];
                w[j+1]=temp1;
            }
        }
    }
    for(int i=0;i<4;i++)
    {
        if(i==3)
            printf("P%d (WT=%d)",p[i],w[i]);
        else
            printf("P%d (WT=%d), ",p[i],w[i]);
    }
    /* Enter your code here. Read input from STDIN. Print output to STDOUT */    
    return 0;
}
