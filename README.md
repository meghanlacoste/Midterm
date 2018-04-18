# Midterm

    package com.company;

// *---------*---------*---------*---------*---------*---------*---------*---------*
// The import statements indicate which of the Java libraries your program will be
// using to complete its task.
//

import java.io.*;
import java.util.*;

public class Main {

    private static int MAX_STRINGS = 2;

    private static void displayProgramInfo(){
        System.out.println("\n======================================================================================== \n");
        System.out.println(" This program will ask the user to input two strings, perform a comparison and display");
        System.out.println(" the result of this comparison to the screen. If you wish to exit the program then please enter");
        System.out.println(" q, or Q to exit");
        System.out.println("\n ======================================================================================== \n");
    }

    public static void main(String[] args) {

        // *---------*---------*---------*---------*---------*---------*---------*
        // Here we are defining the variables that we will need only in the "main" method.
        // The types we use are some of the primitive data types. Recall the primitive data
        // types are: byte, short, int, long, float, double, boolean, and char. It is considered
        // good programming practice to assign a value, using the "=", when the variable is declared.
        //

        String uString1 = null;
        String uString2 =  null;
        int uCount;

        // *---------*---------*---------*---------*---------*---------*---------*
        // Here we are using another class defined in Java, the Scanner class, to
        // allow us to read the input entered by the person running/using our program.
        // Note: We use the keyword "new" infront of the class name "Scanner" to create
        // an "object" from a class. Additionally, we tell our program to specifically
        // create an object that will read information from "System.in". In this case
        // we have called our Scanner object "s"
        //

        Scanner s = new Scanner(System.in);

        // *---------*---------*---------*---------*---------*---------*---------*
        // Here we are "calling" (using the method we created above) to display
        // information about the our program. This is one way we can inform the user
        // what our program will do, and also what is going to be expected from them
        // while they are using our code.
        //

        displayProgramInfo();



        while ( !(s.hasNext("q") || s.hasNext("Q")) ){


            uCount = 1;
            while ( !(s.hasNext("q") || s.hasNext("Q")) || (uCount < MAX_STRINGS) ){
                System.out.println("Enter string # " + uCount + ", or q, or Q to exit");

                switch (uCount){
                    case 1: {
                        uCount++;
                        uString1 = s.next();
                        break;
                    }
                    case 2: {
                        uCount++;
                        uString2 = s.next();
                        break;
                    }
                    default: {
                        System.out.println("ERROR: Unexpected uCount value: " + uCount);
                        System.out.println("       uString1: " + uString1);
                        System.out.println("       uString2: " + uString2);
                        break;
                    }
                } // end switch (uCount)

            } // end while

            System.out.println("Enter q, or Q to exit");

        } // end while

        System.out.println("Thank you good bye.");


    } // end main method

} // end main class
