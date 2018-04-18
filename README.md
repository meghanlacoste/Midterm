# Midterm


import java.util.*;
import java.io.*;

public class Main {

    // create a constant value for use in for loop below
    private static int myMAX = 100;

    public static void main(String[] args) {


        // Declare a variable of String type for user input
        String userFileName;

        int someInteger;

        // *---------*---------*---------*---------*---------*---------*---------*
        // Here we are using another class defined in Java, the Scanner class, to
        // allow us to read the input entered by the person running/using our program.
        // Note: We use the keyword "new" infront of the class name "Scanner" to create
        // an "object" from a class. Additionally, we tell our program to specifically
        // create an object that will read information from "System.in". In this case
        // we have called our Scanner object "s"
        //


        System.out.println("");
        System.out.println("Please type in the file name\n");

        // create a variable s of type scanner to process input from "System.in"
        Scanner scanSystemIn = new Scanner(System.in);

        // Use the Scanner "s" to get the "next" input from "System.in"
        userFileName = scanSystemIn.next();

        // Display the user input now stored in "userInput"
        System.out.println("\nThe user input: " + userFileName);


        // ---------------------------------------------
        // This is where we "try" to process the file
        //

        try {
            // --------------------------------
            // create file, and scanner objects
            // - file object is called tempfilenums.txt and is in your project directory
            //   that is the same folder as the iml file
            //

            File userFile = new File(userFileName);
            Scanner scanUserFile = new Scanner(userFile);

            // ---------------------------------------------
            // Reads in values from the file in a for loop
            //

            for(int i=0; i < myMAX; i++) {

                // ---------------------------------------------
                // The scanner checks if there is another integer and prints it
                // if there is
                //

                if (scanUserFile.hasNext()) {
                    someInteger = scanUserFile.nextInt();
                    System.out.print(" - " + someInteger);
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
