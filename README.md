# First-repo
This is the code for spiral traversal in an square matrix
<br>
import java.util.*;
public class spiraltraversal{
    public static void main(String args[]){
        System.out.println("Enter the number of rows and column of matrix");
        Scanner scn=new Scanner(System.in);
        int m=scn.nextInt();
        int n=scn.nextInt();
        int arr[][]=new int[m][n];
        System.out.println("Enter the elements of matrix");
        for(int i=0;i<arr.length;i++){
            for(int j=0;j<arr[0].length;j++){
                arr[i][j]=scn.nextInt();
            }
        }
        int mincol=0;
        int minrow=0;
        int maxcol=arr[0].length-1;
        int maxrow=arr.length-1;
        int t=n*m;
        int cnt=0;
        while(cnt<t){
            // first column
            for(int i=minrow;i<=maxrow&&cnt<t;i++){
                System.out.print(arr[i][mincol] + " ");
                cnt++;
            }
            mincol++;
            // bottom row
            for(int j=mincol;j<=maxcol&&cnt<t;j++){
                System.out.print(arr[maxrow][j] + " ");
                cnt++; 
            }
            maxrow--;
            // last column
            for(int i=maxrow;i>=minrow&&cnt<t;i--){
                System.out.print(arr[i][maxcol] + " ");
                cnt++;
            }
            maxcol--;
            // firstrow
            for(int j=maxcol;j>=mincol&&cnt<t;j--){
                System.out.print(arr[minrow][j] + " ");
                cnt++;
            }
            minrow++;
        }

    }
}
