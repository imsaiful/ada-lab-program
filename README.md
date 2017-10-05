# ada-lab-program
All Algorithm lab program of AIACTR 5 sem in C



Program 1:
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

Program 2: Insertion Sort
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
Program 3:
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

Program 4: Merge Sort
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
