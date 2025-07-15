# 2Darrays
Give a N * N square matrix A, return an array of its anti-diagonals. Look at the example for more details.

Input 1:
1 2 3
4 5 6
7 8 9

Output 1:
1 0 0
2 4 0
3 5 7
6 8 0
9 0 0
public class Solution {
    public int[][] diagonal(int[][] A) {   // n*m
        int n=A.length;
        int m=A[0].length;

        int[][] ans=new int[m+n-1][m];

        int row=0;
        int col=0;
        int k=0;
        for( col=0;col<m;col++){
          ans[k++] = getDiagonal(A,row,col);
        }

         col=m-1;
        for(row=1;row<n;row++){
          ans[k++] =  getDiagonal(A,row,col);
        }

        return ans;


    }
    public int[] getDiagonal(int[][] A,int row,int col){
        int[] ansRow=new int[A[0].length];
        int k=0;
        while(row<A.length && col>=0 && k<A[0].length){
            ansRow[k++]=A[row++][col--];
        }
        while(k<A[0].length){
            ansRow[k++]=0;
        }
        return ansRow;
    }
}
