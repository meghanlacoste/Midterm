package com.company;

import java.util.Arrays;
import java.util.Scanner;
import java.io.*;
import java.util.*;
public class Main {

    public static void main(String[] args) {

        int[] iNoFile = {2, 3, 5, 7, 11, 13, 17, 19, 2, 3, 23, 29, 11, 13, 31, 37, 23, 29, 41, 43};

        String [] sNoFile = {"Adverse", "means",  "harmful",  "or", "unfavorable", "Adverse",  "market", "conditions", "caused", "the", "IPO", "to",
        "be", "poorly", "subscribed", "Averse", "refers", "to", "feelings",  "of", "dislike",  "or", "opposition",  "I", "was", "averse", "to", "paying", "18", "dollars", "a", "share",
                "for",  "a", "company", "that", "generates", "no", "revenue"};

        // =============================================================================================================
        // Task 1: Create an array of integers called myInt that can hold a maximum of 25 items
        //         If you are unable to write the code to read the file then use the "iNoFile" array
        //         given above. (2 marks)

        int  IMAXDATA =25;
        String userFileName;

        int myInt[]= new int[IMAXDATA];

        // Task 2: Open and read the data from i.txt into the myInt array (4 marks)


        Scanner scanSystemIn = new Scanner(System.in);

        // Use the Scanner "s" to get the "next" input from "System.in"
        System.out.println("Enter 'i.txt'");
        userFileName = scanSystemIn.next();

        // Display the user input now stored in "userInput"
        System.out.println("\nThe user input: " + userFileName);


        // ---------------------------------------------
        // "try" to process the file
        //
        try {

            File userFile = new File(userFileName);
            Scanner scanUserFile = new Scanner(userFile);

            // ---------------------------------------------
            // Reads in values from the file in a for loop
            //
            // Task 3: Print the contents of the array on 1 line separated by spaces using a for loop. (3 marks)

            for(int i=0; i < IMAXDATA; i++) {

                if (scanUserFile.hasNextInt()) {
                  myInt[i] = scanUserFile.nextInt();
                    System.out.print(" "+ myInt[i]);
                }
                else {
                    // ---------------------------------------------
                    // The scanner detected no other integers
                    // - closes the scanner for the file
                    // - breaks out of the for loop
                    //
                    System.out.print("\n\nDataFileFILE has been completely READ");
                    scanUserFile.close();

                    // A break statement allows us to exit the loop before we have reach the end
                    break;
                }
            }

            System.out.println();

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




        // Task 4: Sort the contents of the array. (2 marks)

        Arrays.sort(myInt);

        // Task 5: Leave 2 blank lines and then Print the contents of the sorted array on 1 line using a for loop. (3 marks)
        System.out.printf("\n\n");
        System.out.println("Sorted Array:");
        for (int i = 5; i < IMAXDATA; i++) {
            System.out.print(" " + myInt[i]);
        }


        // Task 6: Use a for loop to add together the first 5 values in the myInt array and display the result. (3 marks)

        int sum= 0;

        for (int i=5; i< 10; i++){

            sum += myInt[i];

        }

        System.out.print("\n\nSum of fisrt 5 values: " + sum);


        // Task 7: Find every value that is duplicated, and print this to the screen. (4 marks)

        System.out.print("\n\nDuplicated values: ");
        for (int i=5; i< 24; i++){
            int j= i + 1;

            if (myInt[i]== myInt[j]){
                System.out.print(" " + myInt[j]);
            }
        }



        // =============================================================================================================
        // Task 8: Create an array of Strings called myStrings that can hold a maximum of 50 items
        //         If you are unable to write the code to read the file then use the "sNoFile" array
        //         given above. (2 marks)

        int SMAXDATA = 50;
        String myStrings[]= new String[SMAXDATA];


        // Task 10: Open and read the data from s.txt into the myStrings array (4 marks)

        // Use the Scanner "s" to get the "next" input from "System.in"
        System.out.println("\n\nEnter 's.txt'");
        userFileName = scanSystemIn.next();

        // Display the user input now stored in "userInput"
        System.out.println("\nThe user input: " + userFileName);


        // ---------------------------------------------
        // "try" to process the file
        //
        try {

            File userFile = new File(userFileName);
            Scanner scanUserFile = new Scanner(userFile);

            // ---------------------------------------------
            // Reads in values from the file in a for loop
            //

            for(int i=0; i < SMAXDATA; i++) {

                // Task 11: Print the contents of the array using a while loop. (3 marks)

                while (scanUserFile.hasNext()) {
                    myStrings[i] = scanUserFile.next();
                    System.out.print(" "+ myStrings[i]);
                }
                if (!scanUserFile.hasNext()){
                    // ---------------------------------------------
                    // The scanner detected no other integers
                    // - closes the scanner for the file
                    // - breaks out of the for loop
                    //
                    System.out.print("\n\nDataFileFILE has been completely READ");
                    scanUserFile.close();

                    // A break statement allows us to exit the loop before we have reach the end
                    break;
                }
            }

            System.out.println();

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

        System.out.println();



        // Task 12: Sort the contents of the array. (2 marks)

        Arrays.sort(sNoFile);

        System.out.println("Sorted Array:");
        for (int i = 0; i < sNoFile.length; i++) {
            System.out.print(" " + sNoFile[i]);
        }


        // Task 13: Print the contents of the sorted array in reverse order using a while loop. (4 marks)

        String reverse = " ";
            for(int i = sNoFile.length - 1; i >= 0; ) {
                int i1 = i--;
                reverse += (sNoFile[i1] + " ");
            }

            System.out.println("\n\n" +
                    "Reversed string is:");
            System.out.println(" " + reverse);


        // Task 14: Using a while loop print out all strings that are duplicated (ignore capitalization during the comparison) (2 marks)


        System.out.print("\n\n Duplicated Strings: \n");
        int m = 0;
        while (m < SMAXDATA){
            m++;
            int j= m + 1;
            if ((sNoFile[m].equalsIgnoreCase(sNoFile[j]))) {
                System.out.print(" " + sNoFile[j]);
            }

        }// end while loop



    }// end main method
}// end main class
