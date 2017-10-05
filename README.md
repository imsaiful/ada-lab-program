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
