# Midterm

  package com.company;

import java.util.Scanner;
import java.util.Arrays;
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


        String userFileName;

       int myInt[] = new int[25];


        // Task 2: Open and read the data from i.txt into the myInt array (4 marks)


        Scanner scanSystemIn = new Scanner(System.in);

        // Use the Scanner "s" to get the "next" input from "System.in"
        System.out.println("Enter 'i.txt'");
        userFileName = scanSystemIn.next();


        // ---------------------------------------------
        // "try" to process the file
        //
        try {

            File userFile = new File(userFileName);
            Scanner scanUserFile = new Scanner(userFile);

            // ---------------------------------------------
            // Reads in values from the file in a for loop
            //

            for(int i=0; i < 24; i++) {


            // Task 3: Print the contents of the array on 1 line separated by spaces using a for loop. (3 marks)

                if (scanUserFile.hasNextInt()) {
                    myInt[i] = scanUserFile.nextInt();
                    System.out.print(" " + myInt[i]);


                }
                else {
                    // ---------------------------------------------
                    // The scanner detected no other integers

                    System.out.print("\n\nDataFileFILE has been completely READ");
                    scanUserFile.close();

                    break;
                }
            }

            System.out.println();

            // if the file could not be found use the catch "e" exception and display message

        } catch (FileNotFoundException e) {
            System.out.println(e);
            e.printStackTrace();
        }

        System.out.println("------------------------------------------------");



        // Task 4: Sort the contents of the array. (2 marks)

        Arrays.sort(myInt);

        // Task 5: Leave 2 blank lines and then Print the contents of the sorted array on 1 line using a for loop. (3 marks)

        System.out.print("\n\n");

        System.out.println("Sorted Array:");
        for (int i = 5; i < 24; i++) {
            System.out.print(" " + myInt[i]);
            }




        // Task 6: Use a for loop to add together the first 5 values in the myInt array and display the result. (3 marks)

        int sum = 0;

        for (int i = 5; i < 10; i++){

            sum+= myInt[i];



        }
        System.out.print("\n \nSum of first 5 digits: " + sum);





        // Task 7: Find every value that is duplicated, and print this to the screen. (4 marks)

        System.out.print("\n\n duplicates: \n");
        for (int i = 5; i < 24; i++) {
            int j = 1 + i;


            if (myInt[i] == myInt[j]){
                System.out.print( " " + myInt[j]);

            }
        }




        // =============================================================================================================
        // Task 8: Create an array of Strings called myStrings that can hold a maximum of 50 items
        //         If you are unable to write the code to read the file then use the "sNoFile" array
        //         given above. (2 marks)


        String myStrings[] = new String[50];


        // Task 10: Open and read the data from s.txt into the myStrings array (4 marks)

        System.out.print("\n\n-------------------------------------------------------------------------------\n");
        System.out.println("Enter 's.txt'");
        userFileName = scanSystemIn.next();


        // ---------------------------------------------
        // "try" to process the file
        //
        try {

            File userFile = new File(userFileName);
            Scanner scanUserFile = new Scanner(userFile);

            // ---------------------------------------------
            // Reads in values from the file in a for loop
            //

            // Task 11: Print the contents of the array using a while loop. (3 marks)

            for (int i=0; i < 49; i++) {


                // Task 3: Print the contents of the array on 1 line separated by spaces using a for loop. (3 marks)

                while (scanUserFile.hasNext()) {
                    myStrings[i] = scanUserFile.next();
                    System.out.print(" " + myStrings[i]);


                }

                if (!scanUserFile.hasNext()) {
                    // ---------------------------------------------
                    // The scanner detected no other integers

                    System.out.print("\n\nDataFileFILE has been completely READ");
                    scanUserFile.close();

                    break;
                }
            }

            System.out.println();

            // if the file could not be found use the catch "e" exception and display message

        } catch (FileNotFoundException e) {
            System.out.println(e);
            e.printStackTrace();
        }

        System.out.println("------------------------------------------------");





        System.out.println("Reverse Sorted Array");


        // Task 12: Sort the contents of the array. (2 marks)

        Arrays.sort(sNoFile);


        // Task 13: Print the contents of the sorted array in reverse order using a while loop. (4 marks)


        for(int i = 0; i < sNoFile.length; i++) {

                    System.out.print(" " + sNoFile[i]); }



      /*

       import java.util.Arrays;

        String [] stringArray = {"ab", "aB", "c", "0", "2", "1Ad", "a10"};
        orderedGuests(stringArray);
    }

    public static void orderedGuests(String[] hotel)
    {
        Arrays.sort(hotel);
        System.out.println(Arrays.toString(hotel));
    }
}






       String reverse = " ";
           for(int i = myStrings.length - 1; i >= 0; i--){

            reverse += myStrings[i];
        }

        System.out.println("Reversed string is:");
        System.out.println(reverse);
        */



        // Task 14: Using a while loop print out all strings that are duplicated (ignore capitalization during the comparison) (2 marks)

        //String myStrings[i] equalsIgnoreCase (String myStrings[j]))

        //static myStrings[i] equalsIgnoreCase(myStrings[i]);

       // String equalsIgnoreCase(String another)










    }
}
