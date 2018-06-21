package com.company;

// *---------*---------*---------*---------*---------*---------*---------*---------*
// The import statements indicate which of the Java libraries your program will be
// using to complete its task.
//

import java.util.*;
import java.io.*;

public class Main {

    // create a constant value for use in for loop below
    private static int myMAX = 100;

    // "line.separator" is a system property that is a platform independent and it is one way
    // of getting a newline from your environment.
    private static String NEWLINE = System.getProperty("line.separator");

    public static void main(String[] args) {

        // --------------------------------
        // create a variable userFileName of type scanner to process input from "System.in"
        //

        String userInputFileName;
        String userOutputFileName;
        String outString;

        int dataArray[] = new int[myMAX];
        int itemCount = 0;
        double average = 0;
        double total = 0;

        System.out.println("");
        System.out.println("Please type in the INPUT file name\n");


        // --------------------------------
        // Here we are using another class defined in Java, the Scanner class, to
        // allow us to read the input entered by the person running/using our program.
        // Note: We use the keyword "new" infront of the class name "Scanner" to create
        // an "object" from a class. Additionally, we tell our program to specifically
        // create an object that will read information from "System.in". In this case
        // we have called our Scanner object "s"
        //

        Scanner scanSystemIn = new Scanner(System.in, "UTF-8");

        // --------------------------------
        // Use the Scanner "userFileName" to get the "next" input from "System.in"
        //

        userInputFileName = scanSystemIn.next();

        // --------------------------------
        // Display the user input now stored in "userInput"
        //

        System.out.println("\nThe user input: " + userInputFileName);

        // ---------------------------------------------
        // This is where we "try" to process the file
        //

        try {

            // --------------------------------
            // create file, and scanner objects
            // - file object is called tempfilenums.txt and is in your project directory
            //   that is the same folder as the iml file
            //

            File userFile = new File(userInputFileName);
            Scanner scanUserFile = new Scanner(userFile, "UTF-8");

            // ---------------------------------------------
            // Reads in values from the file in a for loop
            //

            for(int i=0; i < myMAX; i++) {

                // ---------------------------------------------
                // The scanner checks if there is another integer and prints it
                // if there is
                //

                if (scanUserFile.hasNext()) {

                    dataArray[itemCount] = scanUserFile.nextInt();
                    total = total + dataArray[itemCount];

                    System.out.print(" - " + dataArray[itemCount]);

                    itemCount++;
                }
                else {
                    // ---------------------------------------------
                    // The scanner detected no other integers
                    // - closes the scanner for the file
                    // - breaks out of the for loop
                    //
                    System.out.print("\n\nDataFileFILE has been completely READ\n\n");
                    scanUserFile.close();

                    // A break statement allows us to exit the loop before we have reach the end
                    break;
                }
            }

            // ---------------------------------------------
            // Calculate the Average
            //

            average = total / itemCount;

            // ---------------------------------------------
            // By using the printf statements you can make your output look "neat"
            //

            System.out.println("==================================================================\n");
            System.out.println("                       The Average\n");
            System.out.printf("\tNumber of Items........ %20.0f\n", (double)itemCount);
            System.out.printf("\tSum of all Items:...... %20.0f\n", total);
            System.out.printf("\tAverage:............... %20.4f\n\n", average);
            System.out.println("==================================================================\n");

            // ---------------------------------------------
            // Creating an output file and writing information into it
            //
            // Now that we have read the input file and calculated the average we will store the
            // results in a file using the user input file name and attach a suffix "_out"
            //

            userOutputFileName = userInputFileName.replace(".txt","_out.txt");
            File outputFile = new File(userOutputFileName);

            if (outputFile.createNewFile()){
                System.out.println(userOutputFileName + " was created"); // if file was created
            }
            else {
                System.out.println(userOutputFileName + " existed and is being overwritten."); // if file had already existed
            }

            // --------------------------------
            // If the file creation of access permissions to write into it
            // are incorrect the program throws an exception
            //

            if ((outputFile.isFile()|| outputFile.canWrite())){
                BufferedWriter fileOut = new BufferedWriter(new FileWriter(outputFile));

                fileOut.write("==================================================================");

                fileOut.write(NEWLINE + NEWLINE +"                       The Average" + NEWLINE + NEWLINE);

                outString = NEWLINE + "\t\tNumber of Items........ " + itemCount + NEWLINE;
                fileOut.write(outString);

                outString = "\t\tSum of all Items:...... " + total + NEWLINE;
                fileOut.write(outString);

                outString = "\t\tAverage:............... " + average + NEWLINE + NEWLINE;
                fileOut.write(outString);

                fileOut.write("==================================================================");

                fileOut.close();

            }
            else {
                throw new IOException();
            }

        } // end of try

        // ---------------------------------------------
        // Catch Statements from the try above

        // ---------------------------------------------
        // If the file cannot be found then an exception (error) is generated (thrown) that we have to
        // deal with (catch).
        //
        catch (FileNotFoundException e) {
            System.err.format("File Not Found Exception: %s%n", e);
            e.printStackTrace();
        }

        // ---------------------------------------------
        // If for some reason the output file could not be created we throw an IO Exception
        //
        catch (IOException e) { // in case for some reason the output file could not be created
            System.err.format("IOException: %s%n", e);
            e.printStackTrace();
        }

    }
}
