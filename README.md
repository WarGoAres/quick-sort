# quick-sort
quicksort
#include <stdio.h>
#include<time.h>


void Exchange(int *a, int *b){
 int tmp=*a;
 *a=*b;
 *b=tmp;
}

void QSORT(int *nums, int left, int right){  
    if(left>=right) return; //終止條件
    int l=left+1; //左
    int r=right; //右
    int key=nums[left];
    while(1){
     while(l<=right){
      if(nums[l]>key) break;
      l++;
     }
     while(r>left){
      if(nums[r]<key) break;
      r--;
     }
     if(l>r) break;
     Exchange(&nums[l],&nums[r]); 
    }
    //key 和 相遇的值 互換
    Exchange(&nums[left],&nums[r]);
  //分小組繼續進行
    QSORT(nums,left,r-1);
    QSORT(nums,r+1,right);
}

int main(void){
    
 
 double start,end; 
    
    
    
 start = clock();       
    
        
    

 int array[16]={1,7,6,8,7,4,5,9,78,42,13,14,15,16,77,99};
 QSORT(array,0,15);
 //印出結果
 for(int i=0; i<=15; i++){
  printf("%d ",array[i]);
 }
 
 end = clock();  
  

 double diff = end - start; // ms    
 printf(" %f  ms" , diff);   
 printf(" %f  sec", diff / CLOCKS_PER_SEC );   
 
 
 
 return 0;
 
}


    
   
  



    
	
     
    
     



