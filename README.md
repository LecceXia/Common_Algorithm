# Common_Algorithm

### Binary_Search
if 

array=[2,4,5,6,9] target=6

int find(int[] array,int target){
  int left=0;
  int right=array.length;
  
  while(left<right){
    int mid=left+(right-left)/2;
    if(array[mid]==target) return mid;
    else if(array[mid]<target) left=mid+1;
    else right=mid;
  }
  return -1;
}
