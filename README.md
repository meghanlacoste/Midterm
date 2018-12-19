# Midterm

public class Main {

   package com.company;

import java.util.Random;

public class Main {

    private static int MAXDATA = 30;
    private static int LOWVALUE = 0;
    private static int HIGHVALUE = 100;
    private static int PRIMEVALUE = 7;

    public static void main(String[] args) {

        int[] dataStorage = new int[MAXDATA];
        Random nextValue = new Random();

        // +++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++
        // Generate Random Values

        System.out.println("\nGenerate Random Numbers between " + LOWVALUE + " - " + HIGHVALUE);
        for (int i = 0; i < MAXDATA; i++){
            dataStorage[i] = nextValue.nextInt(HIGHVALUE - LOWVALUE) + LOWVALUE;
        }


        // +++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++
        // Displaying array data in order

        System.out.println("\nDisplay Random Numbers in Order");
        for (int i = 0; i < MAXDATA; i++){
            System.out.println("Index: " + i + " Value: " + dataStorage[i]);
        }

        // +++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++
        // Displaying array data in reverse order

        System.out.println("\nDisplay Random Numbers in Reverse Order");
        for (int i = MAXDATA - 1; i >= 0 ; i--){
            System.out.println("Index: " + i + " Value: " + dataStorage[i]);
        }

        // +++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++
        // Displaying Every 2nd piece of data in the array

        System.out.println("\nDisplay Every 2nd Random Number");
        for (int i = 0; i < MAXDATA; i+=2){
            System.out.println("Index: " + i + " Value: " + dataStorage[i]);
        }

        // +++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++
        // Displaying Every piece of data in the array using an index calculation that uses
        // the first prime number larger than the root of MAXDATA to generate the indices
        // this is an interesting and important concept that can be used to generate a set of
        // values

        System.out.println("\nSolution #1 (use addition) for (6) Display Every 7th Value until all 30 displayed");

        int primeIndex = 0;

        for (int i = 0; i < MAXDATA; i++){

            System.out.println("Item: " + i + " Index: " + primeIndex + " Value: " + dataStorage[primeIndex]);

            // Use the prime value and maximum number of data items to determine the next index
            primeIndex = (primeIndex + PRIMEVALUE) % MAXDATA;

        }

        // +++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++
        // Displaying Every piece of data in the array using an index calculation that uses
        // the first prime number larger than the root of MAXDATA to generate the indices
        // this is an interesting and important concept that can be used to generate a set of
        // values

        System.out.println("\nSolution #2 (use multiplication) for (6) Display Every 7th Value until all 30 displayed");

        primeIndex = 0;

        for (int i = 0; i < MAXDATA; i++){

            // Use the prime value and maximum number of data items to determine the next index
            primeIndex = (PRIMEVALUE * i) % MAXDATA;

            System.out.println("Item: " + i + " Index: " + primeIndex + " Value: " + dataStorage[primeIndex]);

        }


        // +++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++
        // Displaying Every piece of data in the array using an index calculation that uses
        // the first prime number larger than the root of MAXDATA to generate the indices
        // this is an interesting and important concept that can be used to generate a set of
        // values

        System.out.println("\nSolution #3 for (6) Display Every 7th Value until all 30 displayed");
        System.out.println("\n\t Instead of having the calculation on a seperate line it is done with println");

        primeIndex = 0;

        for (int i = 0; i < MAXDATA; i++){

            System.out.println("Item: " + i + " Index: " + ((PRIMEVALUE * i) % MAXDATA) + " Value: " + dataStorage[((PRIMEVALUE * i) % MAXDATA)]);

        }

    }
}
