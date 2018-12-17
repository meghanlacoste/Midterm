public class Main {
   private static int MAXLOOP1 = 20;
   private static int MAXLOOP2 = 5;
   private static int MAXLOOP3 = 10;
    private static int MAXLOOP4 = 7;
    private static int MAXLOOP5 = 97;
     private static int MAXPERLINE1 = 20;
    private static int MAXPERLINE2 = 50;
    private static int MODULUS = 3;
     public static void main(String[] args) {
     
     System.out.println("*---------*---------*---------*---------*---------*---------*");
     int product = 0;
     int itemsOnLine =  0;
         for (int i = 1; i <= MAXLOOP1; i++){
             for (int j = 1; j <= MAXLOOP2; j++){
                 itemsOnLine++;
                product = i * j;
                 System.out.print( product + " ");
                 if (itemsOnLine == MAXPERLINE1){
                    System.out.println();
                    itemsOnLine = 0;
                } // end if (itemsOnLine == MAXPERLINE)
             } // end for (int j = 1; j <= MAXLOOP2; j++)
        } // end for (int i = 1; i <= MAXLOOP1; i++)
         System.out.println("*---------*---------*---------*---------*---------*---------*");
         product = 0;
        itemsOnLine =  0;
         int idx1 = 1;
        int idx2 = 1;
         for (int i = 1; i <= MAXLOOP3; i++){
             idx1 = 1;
             while (idx1 < MAXLOOP4 ){
                 idx2 = 1;
                 do {
                     product = i * idx1 * idx2;
                     if (product % MODULUS == 0){
                         itemsOnLine++;
                         System.out.print( product + " ");
                         if (itemsOnLine == MAXPERLINE2){
                             System.out.println();
                            itemsOnLine = 0;
                         } // end if (itemsOnLine == MAXPERLINE)
                    } // end if (product % MODULUS == 0)
                     idx2++;
                } while (idx2 <= MAXLOOP5);
                 idx1++;
             } // end while (idx1 < MAXLOOP4 )
        } // end (int i = 1; i <= MAXLOOP3; i++)
         System.out.println("*---------*---------*---------*---------*---------*---------*");
     } // end main method
} // end main class

    }
}
