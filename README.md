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

### Example 1: Fibonacci sequence
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
### Example 2: Stair Jumps 
You can only jump one or two steps at a time. There are several ways to jump to n steps  
For the nth step, you can only jump from the n-1 or n-2 steps which means f(n)=f(n-1)+f(n-2). So this is the same as Fibonacci sequence.  
For example, we are now on the 6th stair, so we can only jump to this stair from 6-2=4th stair or 6-1=5th stair which means f(6)=f(4)+f(5).(this question is equal to "How many ways to fill a 2*n rectangle with 2*1 rectangle", because we can use 2*1 to fill or use 1*2 to fill) 

### Example 3: Knapsack problem(The most important thing in dynamic programming is to find the state transfer equation) 
The total capacity of a backpack is V, and now there are N items, the weight of the i item is weight[i], and the value is value[i]
Then, how to load things into the backpack can maximize the total value of the items in the bag. There are three main ways to load items here:  
1.  0-1 backpack: each item can only be loaded at most once  
2.  Multiple backpacks: each category has a limit on the number of items, the category i can be loaded up to num[i] times  
3.  Complete backpack: each item can be packed into the bag an unlimited number of times  

#### 0-1 backpack
dp[i][j] represents the maximum value of the sum of the value of the first i items that can be loaded into a backpack of capacity j  
Suppose we have found that the maximum value of the value of the first i-1 item loaded into the backpack of capacity j is dp[i-1][j], and the value of the fixed capacity j is unchanged, then the method of loading the i item The discussion is as follows:  
1.  if weight[i]>j, we can not load the item into the backpack,so dp[i-1][j]=dp[i][j]  
2.  if weight[i]<=j, we can load the item into the bakcpack, so dp[i][j]=dp[i-1][j-weight[i]]+value[i]  
Then we should jugde if the i-th item is loaded into a backpack with a capacity of j, whether the total value in the backpack is the largest. So we should compare dp[i-1][j] and dp[i-1][j-weight[i]]+value[i]  
As for the item number, we can judge if dp[i][j]>dp[i-1[j], the i th item must be loaded into backpack  
```
* 0-1背包问题
     * @param V 背包容量
     * @param N 物品种类
     * @param weight 物品重量
     * @param value 物品价值
     * @return
     */
    public static int ZeroOnePack(int V,int N,int[] weight,int[] value){
        int[][] dp = new int[N+1][V+1];
        for(int i=1;i<N+1;i++){
            for(int j=1;j<V+1;j++){
                //由于weight和value数组下标都是从0开始,注意第i个物品的重量为weight[i-1],价值为value[i-1]
                if(weight[i-1] > j)
                    dp[i][j] = dp[i-1][j];
                else
                    dp[i][j] = Math.max(dp[i-1][j],dp[i-1][j-weight[i-1]]+value[i-1]);
            }
        }
      return dp[N][V];
      }
```



  



## Greedy Algorithm


## Branch and Bound


## Divide and Conquer


