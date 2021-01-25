# Doing this topic by watching Aditya Verma Dp series, BackToBackSWE & Anuj Bhaiya videos
Approach to follow till gaining confidence with top down:
<br>
1) Write Recursive code<br>
2) Memoize it<br>
3) Write the Top Down code<br>
## Chapter 1: 0/1 Knapsack
### Basic Problem: [0/1 Knapsack](https://www.interviewbit.com/problems/0-1-knapsack/)
```java
//Recursion Only
public int knapsack(int[] values, int[] weights, int capacity, int n){
        //base case
        if(n==0 || capacity==0) return 0;
        //choice diagram
        if(weights[n-1]<=capacity){
            return 
            Math.max(values[n-1]+knapsack(values, weights, capacity-weights[n-1], n-1), 
            knapsack(values, weights, capacity, n-1));
        }
        else return knapsack(values, weights, capacity, n-1);
    }
```
```java
//Recursion with memoisation
//initialise the dp array to -1 first
public int knapsack(int[] values, int[] weights, int capacity, int n, int dp[][]){
        //base case
        if(n==0 || capacity==0) return 0;
        
        if(dp[n-1][capacity]!=-1) return dp[n-1][capacity];
        //memoize
        //choice diagram
        
        if(weights[n-1]<=capacity){
            //check if this already exists
            
            dp[n-1][capacity]=
            Math.max(values[n-1]+knapsack(values, weights, capacity-weights[n-1], n-1, dp), 
            knapsack(values, weights, capacity, n-1, dp));
            return dp[n-1][capacity];
        }
        else {
            dp[n-1][capacity]=knapsack(values, weights, capacity, n-1, dp);
            return dp[n-1][capacity];
        }
    }
```
```java
//Recursion with memoisation vs Top Down
```
```java
//Bottom Up/Tabulation
```
### Variation 1: [Subset Sum Problem](https://www.interviewbit.com/problems/subset-sum-problem/)
```java
//only recursion
public int subset(int[] values, int target, int n){
        //base case
        if(n==0 && target>0) return 0;
        if(target==0) return 1;
        
        //choice 
        if(values[n]<=target){
           return Math.max(subset(values, target-values[n], n-1), subset(values, target, n-1));
        }
        else {
            return subset(values, target, n-1);
        }
    }
```
```java
//recursion + memoization
public int subset(int[] values, int target, int n, int dp[][]){
        //base case
        if(n==0 && target>0) return 0;
        if(target==0) return 1;
        if(dp[n][target]!=-1) return dp[n][target];
        //choice 
        if(values[n]<=target){
            dp[n][target]=Math.max(subset(values, target-values[n], n-1, dp), subset(values, target, n-1, dp));
            return dp[n][target];
        }
        else {
            dp[n][target]=subset(values, target, n-1, dp);
            return dp[n][target];
        }
    }
```
### Variation 2: [Equal Sum Partition Problem]()
