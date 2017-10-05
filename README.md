# ada-lab-program
All Algorithm lab program of AIACTR 5 sem in C



Program 1:Bubble Sort Algorithm
```
#include<stdio.h>
int main()
{
  int n;
  int a[20];
  printf("Enter the number of element \n");//enter the number of element
  scanf("%d",&n);
  printf("Enter the element \n");
  for(int i=0;i<n;i++)
    {
      scanf("%d",&a[i]);//input array
    }
  for(int i=0;i<n-1;i++)//bubble sort algorithm 
    {
      for(int j=1;j<=n-i-1;j++)
        {
          if(a[j]<a[j-1])
            {
              int temp=a[j];
              a[j]=a[j-1];
              a[j-1]=temp;
            }
        }
     }
  for(int i=0;i<n;i++)
    {
      printf("%d \t", a[i]);//printing the sorted element
    }
return 0;
}
```
![alt text](https://github.com/imsaiful/ada-lab-program/blob/master/Screenshot%20from%202017-10-05%2012-10-35.png)


Program 2: Insertion Sort Algorithm
```
#include<stdio.h>
int main()
{
  int n;
  int a[20];
  printf("Enter the number of element \n");//enter the number of element
  scanf("%d",&n);
  printf("Enter the element \n");
  for(int i=0;i<n;i++)
    {
      scanf("%d",&a[i]);//input array
    }
  for(int i=0;i<n-1;i++)//Insertion sort algorithm
    {
      for(int j=i;j>=0;j--)
        {
          if(a[j]>a[j+1])
            {
              int temp=a[j];
              a[j]=a[j+1];
              a[j+1]=temp;
            }

        }
     }
  for(int i=0;i<n;i++)
    {
      printf("%d \t", a[i]);//printing the sorted element
    }
return 0;
}

```
![alt text](https://github.com/imsaiful/ada-lab-program/blob/master/Screenshot%20from%202017-10-05%2012-29-04.png)


Program 3: Quick Sort Algorithm
```
#include<stdio.h>
void QuickAlgo(int [],int  ,int );
int main()
{
    int n,a[20];
    printf("Enter the number of element \n");
    scanf("%d",&n);
    printf("Enter the element \n");
    for(int i=0;i<n;i++)
    {
        scanf("%d",&a[i]);
    }
    QuickAlgo(a,0,n-1);
    for(int i=0;i<n;i++)
    {
        printf("%d \t",a[i]);
    }
    return 0;
}
    void QuickAlgo(int a[],int low,int high)
    {
        int loc,i,j;
        if(low<high)
        {
            i=low;
            j=high;
            loc=low;
            while(i<j)
            {
                while(a[i]<=a[loc] && i<=high)
                    {
                        i++;
                    }
                while(a[j]>a[loc] && j>=low)
                    {
                        j--;
                    }
                if(i<j)
                {
                    int temp=a[i];
                    a[i]=a[j];
                    a[j]=temp;
                }
            }
            int temp=a[j];
            a[j]=a[loc];
            a[loc]=temp;
            QuickAlgo(a,low,j-1);
            QuickAlgo(a,j+1,high);



        }
}
```
![alt text](https://github.com/imsaiful/ada-lab-program/blob/master/Screenshot%20from%202017-10-05%2015-00-44.png)


Program 4: Merge Sort Algorithm
```
#include<stdio.h>
void sort(int[], int , int );
    /* Main method */

    int main()
    {

        int n, i;
        int a[20];
        /* Accept number of elements */
        printf("Enter the number of element\n");
        scanf("%d",&n);
        /* Accept elements */
        printf("Enter integer elements\n");
        for (i = 0; i < n; i++)
        {
            scanf("%d",&a[i]);
        }
        /* Call method sort */
        sort(a, 0, n);
        /* Print sorted Array */
        printf("\nElements after sorting\n");
        for (i = 0; i < n; i++)
        {
                printf("%d \t",a[i]);
        }
        return 0;
    }
void sort(int a[], int low, int high)
    {
        int N = high - low;
        if (N <= 1)
            return;
        int mid = low + N/2;
        // recursively sort
        sort(a, low, mid);
        sort(a, mid, high);
        // merge two sorted subarrays
        int temp[N];
        int i = low, j = mid;
        for (int k = 0; k < N; k++)
        {
            if (i == mid)
                temp[k] = a[j++];
            else if (j == high)
                temp[k] = a[i++];
            else if (a[j]<a[i])
                temp[k] = a[j++];
            else
                temp[k] = a[i++];
        }
        for (int k = 0; k < N; k++)
            a[low + k] = temp[k];
    }
```
![alt text](https://github.com/imsaiful/ada-lab-program/blob/master/Screenshot%20from%202017-10-05%2015-36-22.png)


Program 5: Matrix Multiplication
```
#include<stdio.h>
int main()
{
    int m1,n1,m2,n2,a[10][10],b[10][10],c[10][10];
    int i,j,k;
    printf("Enter the Number of row and column of matrix 1 \n");
    scanf("%d%d",&m1,&n1);
    printf("Enter the Number of row and column of matrix 2 \n");
    scanf("%d%d",&m2,&n2);
    printf("Enter the element of matrix 1 \n");
    for(i=0;i<m1;i++)
    {
        for(j=0;j<n1;j++)
        {
            scanf("%d",&a[i][j]);
        }
    }
    printf("Enter the element of the matrix 2 \n");
    for(i=0;i<m2;i++)
    {
        for(j=0;j<n2;j++)
        {
            scanf("%d",&b[i][j]);
        }
    }
    printf("Matrix 1 is given by \n");
     for(i=0;i<m1;i++)
     {
        for(j=0;j<n1;j++)
        {
            printf("%d \t",a[i][j]);
        }
        printf("\n");
     }
     printf("Matrix 2 is given by \n");
     for(i=0;i<m1;i++)
     {
        for(j=0;j<n2;j++)
        {
            printf("%d \t",b[i][j]);
        }
        printf("\n");
     }
     if(n1==m2)
     {
     for(i=0;i<m1;i++)
     {
        for(j=0;j<n2;j++)
            {
            c[i][j]=0;
                for(k=0;k<m2;k++)
                {
                    c[i][j]=c[i][j]+a[i][k]*b[k][j];

                }

            }
     }
     printf("Matrix Multiplication is given by \n");
     for(i=0;i<m1;i++)
     {
        for(j=0;j<n2;j++)
        {
            printf("%d \t",c[i][j]);
        }
        printf("\n");
     }
     }
     else
     {
        printf("Matrix multiplication is not possible");
     }
     return 0;
}
```
![alt text](https://github.com/imsaiful/ada-lab-program/blob/master/Screenshot%20from%202017-10-05%2023-47-48.png)


Program 6: Stressen Matrix Multiplication
```
#include<stdio.h>
int main()
{
    int a[2][2],b[2][2],c[2][2];
    int i,j;
    printf("Enter the element of matrix 1 \n");
    for(i=0;i<2;i++)
    {
        for(j=0;j<2;j++)
        {
            scanf("%d",&a[i][j]);
        }
    }
    printf("Enter the element of the matrix 2 \n");
    for(i=0;i<2;i++)
    {
        for(j=0;j<2;j++)
        {
            scanf("%d",&b[i][j]);
        }
    }
    printf("Matrix 1 is given by \n");
     for(i=0;i<2;i++)
     {
        for(j=0;j<2;j++)
        {
            printf("%d \t",a[i][j]);
        }
        printf("\n");
     }
     printf("Matrix 2 is given by \n");
     for(i=0;i<2;i++)
     {
        for(j=0;j<2;j++)
        {
            printf("%d \t",b[i][j]);
        }
        printf("\n");
     }
     int p=(a[0][0]+a[1][1])*(b[0][0]+b[1][1]);
     int q=(a[1][0]+a[1][1])*b[0][0];
     int r=a[0][0]*(b[0][1]-b[1][1]);
     int s=a[1][1]*(b[1][0]-b[0][0]);
     int t=(a[0][0]+a[0][1])*b[1][1];
     int u=(a[0][0]-a[1][0])*(b[0][0]+b[0][1]);
     int v=(a[0][1]-a[1][1])*(b[1][0]+b[1][1]);
     c[0][0]=p+s-t+v;
     c[0][1]=r+t;
     c[1][0]=q+s;
     c[1][1]=p+r-q-u;
     printf("Matrix Multiplication is given by \n");
     for(i=0;i<2;i++)
     {
        for(j=0;j<2;j++)
        {
            printf("%d \t",c[i][j]);
        }
        printf("\n");
     }
     return 0;
     }

```
![alt text](https://github.com/imsaiful/ada-lab-program/blob/master/Screenshot%20from%202017-10-06%2000-13-35.png)


Program 7: Longest Common Subsequence
```
#include<stdio.h>
#include<string.h>
int max(int , int);
void Lcs(char *a,char *b)
{
int m=strlen(a);
int n=strlen(b);
int c[m+1][n+1];
for(int i=0;i<=m;i++)
{
    for(int j=0;j<=n;j++)
    {
        if(i==0 || j==0)
        {
            c[i][j]=0;
        }
        else if(a[i-1]==b[j-1])
        {
            c[i][j]=c[i-1][j-1]+1;
        }
        else
        {
            c[i][j]=max(c[i-1][j],c[i][j-1]);
        }
    }
}
int index=c[m][n];
char res[index+1];
res[index]='\0';
int i=m,j=n,k=index;
while(i>0 && j>0)
{
    if(a[i-1]==b[j-1])
    {
        res[index-1]=a[i-1];
        i--;
        j--;
        index--;
    }
    else if(c[i-1][j]>c[i][j-1])
    {
        i--;
    }
    else
    {
        j--;
    }
}
puts(res);
}
int max(int x,int y)
{
    return (x>y)?x:y;
}
int main()
{
char a[20],b[20];
printf("Enter the String 1");
scanf("%s",a);
printf("Enter the String 2");
scanf("%s",b);
Lcs(a,b);
return 0;
}

```
![alt text](https://github.com/imsaiful/ada-lab-program/blob/master/Screenshot%20from%202017-10-06%2001-06-53.png)
