# CONVERSION-OF-2D-ARRAY-TO-1D-ARRAY-AND-FINDING-MEDIAN
import java.util.*;
class HelloWorld {
    public static void main(String[] args) {
        Scanner sc=new Scanner(System.in);
        int n=sc.nextInt();
        int [][]a=new int[n][n];
        int []b=new int[n*n];
        System.out.println("Enter array values :");
        int k=0;
        for(int i=0;i<n;i++){
            for(int j=0;j<n;j++){
                int p=sc.nextInt();
                a[i][j]=p;
                b[k]=p;
                k++;
            }
        }
        for(int i=0;i<n*n;i++){
            for(int j=0;j<n*n;j++){
                if(b[i]<b[j]){
                    int temp=b[i];
                    b[i]=b[j];
                    b[j]=temp;
                }
            }
        }
        System.out.println("Sorted array after converting :");
        for(int i=0;i<n*n;i++){
            System.out.print(" "+b[i]);
        }
         System.out.println();
        if ((n*n)%2!=0){
            int ind=(n*n)/2;
            System.out.println(" Median :"+b[ind]);
        }
        else{
            int m=(b[(n*n)/2]+b[((n*n)/2-1)])/2;
            System.out.println(" Median :"+m);
        }
    }
}
