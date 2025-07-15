Problem Description

You are given an array A of N elements. Find the number of triplets i,j and k such that i<j<k and A[i]<A[j]<A[k]


Problem Constraints

1 <= N <= 103
1 <= A[i] <= 109


Input Format

First argument A is an array of integers.


Output Format

Return an integer.


Example Input

Input 1:
A = [1, 2, 4, 3]
Input 2:
A = [2, 1, 2, 3]


Example Output

Output 1:
2
Output 2:
1



//BRUTEFORCE

public class Solution {
    public int solve(int[] A) {
int count=0;
        for(int i=0;i<A.length-2;i++){
            for(int j=1;j<A.length-1;j++){
                for(int k=2;k<A.length;k++){
                    if((i<j) && j<k  &&  A[i]<A[j] && A[j]<A[k] ){
                        count++;
                 }
                }
            }
        }
        return count;
    }
}

//OPTIMISED SOLUTION

public class Solution {
    public int solve(int[] A) {
        int ans=0;
        int n=A.length;
       
       for(int i=1;i<n-1;i++){
           int left=0,right=0;

           for(int k=0;k<i;k++){
               if(A[k]<A[i]) left++;
           }

           for(int k=i+1;k<n;k++){
               if(A[k]>A[i]) right++;
           }

           ans+=right*left;
       }
       return ans;
    }
}
