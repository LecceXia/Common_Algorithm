# Common_Algorithm

Some interesting algorithms  

## Binary_Search
if you want to Find value = target

```java
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
```

## Backtracking

Backtracking is another "enumeration algorithm".  
  
For example, there is a tree. The first layer of the tree has 8 nodes, and the second layer of the tree has 5 nodes. So if we start from the root, we can first choose a node from the first layer that meets the condition(The condition means what we expect), and then we get through the first layer and will face the second layer. We should choose a node from the second layer that meets the condition.  
  
1. If all the 5 nodes can not meet the condition, we should back to the first layer and reselect a node from the layer----this means Backtracking.  
  
2. If one of the nodes can meet the condition, we should go on our process---go to the next layer  
  
If we want all the solution, the condition that we can end the process is that we back to the root and all the nodes have been traversed.

If we only want one solution, we can end when we get one solution.

### *Algorithm Framework*  
Suppose the solution of the problem is an n-dimensional vector (a1, a2, ..., an), and the constraint is that ai (i = 1, 2, 3, ..., n) satisfies a certain condition, denoted as f (ai).  
1.  Non-recursive  
```
int a[n],i;
i=1; 
while(i>0 and )
```
## Dynamic Programming


## Greedy Algorithm


## Branch and Bound


### Divide and Conquer


