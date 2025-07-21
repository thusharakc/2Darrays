Problem Description

You are given a n x n 2D matrix A representing an image.

Rotate the image by 90 degrees (clockwise).

You need to do this in place.

Note: If you end up using an additional array, you will only receive partial score.

public class Solution {
    public void solve(int[][] A) {
        //to rorate by 90 deg we need to take transpose and then reverse each row

        // takking transpose
        int n=A.length;
        
        for(int i=0;i<n-1;i++){
            for(int j=i+1;j<n;j++){
                int temp=A[i][j];
                A[i][j]=A[j][i];
                A[j][i]=temp;
            }
            
        }
            //now A is transpose of original array
            //next step is to rorate each row
            for(int i=0;i<n;i++)
           { int colLeft=0,colRight=n-1;
            while(colLeft<colRight){
                 int temp=A[i][colLeft];
                A[i][colLeft]=A[i][colRight];
                A[i][colRight]=temp;             

                colLeft++;colRight--;
            }
            }
    }
}
