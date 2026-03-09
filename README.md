import java.util.Scanner;
class javawork{
    public static void main(String[] args) {
        Scanner sc=new Scanner(System.in);
        System.out.println("Enter the dimension of matrix:");
        int n=sc.nextInt();
        int [][]matrix=new int[n][n];
        System.out.println("Enter matrix elements:");
        for (int i= 0; i < n; i++) {
            for (int j = 0; j < n; j++) {
                matrix[i][j]=sc.nextInt();   
            }
        }       
        int sum=0;
        for(int j=0;j<n;j++){
            sum+=matrix[0][j];
        }
        boolean ismagic=true;
        for(int i=0;i<n;i++){
            int rowsum=0;
            int colsum=0;
            for(int j=0;j<n;j++){
                rowsum+=matrix[i][j];
                colsum+=matrix[j][i];
            }
            if(rowsum!=sum||colsum!=sum){
                ismagic=false;
                break;
            }
        }
            int diag1=0;
         for (int i = 0;i < n; i++) {
             diag1+=matrix[i][i];
         }
            int diag2=0;
            for (int i = 0;i< n; i++) {
                diag2+=matrix[i][n-i-1];   
            }
            if(diag1!=sum||diag2!=sum){
                ismagic=false;
            }
        if(ismagic)
            {
            System.out.println("this is magic matrix");
        }
        else{
            System.out.println("this is not magic square");
        }
        
        }
    }
