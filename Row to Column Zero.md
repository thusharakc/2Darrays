You are given a 2D integer matrix A, make all the elements in a row or column zero if the A[i][j] = 0. Specifically, make entire ith row and jth column zero.


Input 1:

[1,2,3,4]
[5,6,7,0]
[9,2,0,4]

Output 1:

[1,2,0,0]
[0,0,0,0]
[0,0,0,0]




// IMP:  here while making -1 in each row and column, only change non zero values to -1.
public class Solution {
    public int[][] solve(int[][] A) {
        int row=A.length;
        int col=A[0].length;

        //fst go to each row and if 0 present then make it to -1
      
        for(int i=0;i<row;i++){

            for(int j=0;j<col;j++){
                if(A[i][j]==0)
                  {makeRowChange(A,i,-1,0);
                  break;}
            }
        } 
        //check in each column also
        for(int j=0;j<col;j++){
            
            for(int i=0;i<row;i++){
              
                if(A[i][j]==0)
               {  
                    makeColChange(A,j,-1,0);
                break;}
            }
        }
        
 //fst go to each row and if 0 present then make it to -1
        for(int i=0;i<row;i++){
            for(int j=0;j<col;j++){
                if(A[i][j]==-1)
                  A[i][j]=0;
            }
        }

        


        return A;
    }

    public void makeRowChange(int[][] A,int row,int val,int orig){
        
        for(int col=0;col<A[0].length;col++ ){
               if((A[row][col])!=orig)  A[row][col]=val;
        }
    }

        public void makeColChange(int[][] A,int col,int val,int orig){
        
        for(int row=0;row<A.length;row++ ){
            if((A[row][col])!=orig)  A[row][col]=val;
        }
    }

}
