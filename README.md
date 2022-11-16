# Quick-sort-in-C
# include<stdio.h>
void swap(int *a , int *b){
    int c;
    c = *a;
    *a = *b;
    *b = c;
}
int Partition(int a[],int lb , int ub){
    int pivot = a[lb];
    int start = lb;
    int end = ub;
    while(start < end){
        while(a[start] <= pivot)
        {
            start ++ ;
        }
        while(a[end] > pivot)
        {
            end -- ;
        }
        if(start < end)
        {
            swap(&a[start] , &a[end]);
        }
    }
    swap(&a[lb],&a[end]);
    return end;
}
void QuickSort(int a[],int lb,int ub)
{
    if(lb < ub)
    {
        int loc;
        loc = Partition(a,lb,ub);
        QuickSort(a,lb,loc-1);
        QuickSort(a,loc+1,ub);
        
    }
}
int main() 
{
  int A[20],n,lb,ub,i;
  printf("Enter the number of elements\n");
  scanf("%d",&n);
  printf("Enter the elements\n");
  for( i=0 ; i<n ; i++){
    scanf("%d",&A[i]);
  }
   QuickSort(A,0,n-1);
  for(i=0;i<n;i++){
    printf("%d\t",A[i]);
  }
  return 0;
}
