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
2.  Recursive
```
int a[n];
try(int i)
{
    if(i>n)
       // input the result;
     else
    {
       for(j = ; j <= ; j++)  // enumerate all the possible paths
       {
           if(condition(j))                 // meet the condition
             {
                a[i] = j;
              ...                         // other operations
                try(i+1);
              }
         }
     }
}
```
## Dynamic Programming  

Every decision is made on the current state, I think it is just like HMM(Hidden Markov Model)  
  
what we should pay attention to:
1.  the stage of the problem
2.  the state of every stage
3.  The recursive relationship between the transformation from the previous stage to the latter stage

### example1: Fibonacci sequence
```
int fibo(int n){
  if(n=0) return 0;
  if(n=1) return 1;
  else{
    int[] result=new int[n+1];
    result[0]=0;
    result[1]=1;
    for(int=2;i<=n;i++){
      result[i]=reuslt[i-1]+result[i-2];
    }
    return result[n];
  }
}
```

## Greedy Algorithm


## Branch and Bound


### Divide and Conquer


