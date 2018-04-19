# Midterm

package com.company;

// -------------------------------------------------------------------------------
// Bring in the appropriate Java libraries
//

import java.util.*;
import java.io.*;

public class Main {

    // Declare Constant Values
    public static int maxArr = 20;
    public static int INVALID = -1;

    // The main method
    public static void main(String[] args) {

        int a[][] = new int[maxArr][maxArr];
        boolean fileDone = false;

        // -------------------------------------------------------------------------------
        // Initialize the array to a known value
        // - loops over each row using "i",
        // - loops over the columns using "j"
        // -  sets all array values to INVALID
        //

        for(int i=0; i < maxArr; i++) {
            for(int j = 0; j < maxArr; j++){
                a[i][j] = INVALID;
            }
        }

        System.out.println("------------------------------------------------");

        try {
            // --------------------------------
            // create file, and scanner objects
            // - file object is called tempfilenums.txt and is in your project directory
            //   that is the same folder as the iml file
            //
            File f = new File("tempfilenums.txt");
            Scanner s = new Scanner(f);

            // ---------------------------------------------
            // Reads in values from the file into the array
            // - can only hold maxArr * maxArr elements
            // - reads file data into array integer by integer filling array sequentially
            //

            for(int i=0; i < maxArr; i++) {

                for(int j = 0; j < maxArr; j++){

                    // ---------------------------------------------
                    // The scanner checks if there is another integer and prints it
                    // if there is
                    //

                    if (s.hasNext()) {
                        a[i][j] = s.nextInt();
                        System.out.print(" - " + a[i][j]);
                    }
                    else {
                        // ---------------------------------------------
                        // The scanner detected no other integers
                        // - sets boolean "fileDone" to true
                        // - closes the scanner
                        // - breaks out of the for loop
                        //

                        fileDone = true;
                        s.close();
                        break;
                    }
                }

                // ---------------------------------------------
                // The file has been completely read into the array, so the user is notified.
                //

                System.out.println();
                if (fileDone) {
                    System.out.println("\n\tFile data has been read into array");
                    break;
                }
            }

            // ---------------------------------------------
            // If there is not enough space in the array so make sure the user is notified that the file contains
            // more data than the array can hold.
            //

            if (!fileDone) {
                System.out.println("\n\tCAUTION: file has additional data, consider making array larger.");
            }

            // ---------------------------------------------
            // If the file cannot be found then an exception (error) is generated (thrown) that we have to
            // deal with (catch).
            // - we print "e" the exception, and
            // - show the user where it was using the "exceptions" stack trace information
            //

        } catch (FileNotFoundException e) {
            System.out.println(e);
            e.printStackTrace();
        }

        System.out.println("------------------------------------------------");

/// ANOTHER STRATAGy
//you can take the help of Set collection

int end = arr.length;
Set<Integer> set = new HashSet<Integer>();

for(int i = 0; i < end; i++){
  set.add(arr[i]);
}
//now if you will iterate through this set, it will contain only unique values. Iterating code is like this :

Iterator it = set.iterator();
while(it.hasNext()) {
  System.out.println(it.next());
}
    }
}
