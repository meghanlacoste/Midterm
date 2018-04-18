When you have grouped a bunch of similar items together into an array, one of the things you can do easily is rearrange items. The following statements switch the values of two elements in an integer array called numbers:

int temp = numbers[5];
numbers[5] = numbers[6];
numbers[6] = temp;
These statements result in numbers[5] and numbers[6] trading values with each other. The integer variable called temp is used as a temporary storage place for one of the values being swapped.

The most common reason to rearrange elements of an array is to sort them into a specific order. Sorting is the process of arranging a list of related items into a set order. An example would be sorting a list of numbers from lowest to highest.

Santa Claus, the world's biggest user of lists, might want to use sorting to rearrange the order of gift recipients according to last name. This order could determine who receives gifts first on Christmas Eve, with people such as Willie Aames and Paul Azinger raking in their Yuletide plunder much earlier than alphabetical unfortunates such as Dweezil Zappa and Jim Zorn. (As someone whose last name begins with "C," I'm not necessarily opposed to this practice).

Sorting an array is easy in Java because the Arrays class does all of the work for you. Arrays, which is part of the java.util group of classes, can rearrange arrays of all variable types as well as strings.

To use the Arrays class in a program to sort an array, undertake the following steps:

Use the import java.util.*; statement to make all of the java.util classes available in the program.

Create the array.

Use the sort() method of the Arrays class to rearrange an array.

An array of variables that is sorted by the Arrays class will be rearranged into ascending numerical order. This will be easy to see with an array of numbers such as float values. Characters and strings will be arranged according to the alphabet, with the first letters such as A, B, and C coming first, and the last letters such as X, Y, and Z coming last.

Listing 9.2 contains a short program that sorts five names. Enter this with your word processor and save the file as Name.java. Make sure not to overlook Line 1. If you do, the program will fail to compile because the Arrays class in Line 11 can't be found.

Listing 9.2 The Full Source Code of Name.java
 1: import java.util.*;
 2:
 3: class Name {
 4:   public static void main(String[] arguments) {
 5:     String names[] = { "Peter", "Patricia", "Hunter", "Sarah",
 6:       "Gabe", "Gina", "Rob", "John", "Zoey", "Tammy", "Robert",
 7:       "Sean", "Paschal", "Kathy", "Neleh", "Vecepia" };
 8:     System.out.println("The original order:");
 9:     for (int i = 0; i < names.length; i++)
10:       System.out.println(i + ": " + names[i]);
11:     Arrays.sort(names);
12:     System.out.println("The new order:");
13:     for (int i = 0; i < names.length; i++)
14:       System.out.println(i + ": " + names[i]);
15:   }
16: }
After you have created this source file, compile it. Using the SDK, you can compile it at a command line by entering this command:

javac Name.java
This Java program displays a list of five names in their original order, sorts the names, and then redisplays the list.

The following output is produced:

The original order:
0: Peter
1: Patricia
2: Hunter
3: Sarah
4: Gabe
5: Gina
6: Rob
7: John
8: Zoey
9: Tammy
10: Robert
11: Sean
12: Paschal
13: Kathy
14: Neleh
15: Vecepia
The new order:
0: Gabe
1: Gina
2: Hunter
3: John
4: Kathy
5: Neleh
6: Paschal
7: Patricia
8: Peter
9: Rob
10: Robert
11: Sarah
12: Sean
13: Tammy
14: Vecepia
15: Zoey
When you're working with strings and the basic types of variables such as integers and floating-point numbers, you can only sort them by ascending order using the Arrays class. You can write code to do your own sorts by hand if you desire a different arrangement of elements during a sort, or if you want better efficiency than the Arrays class provides.
//
//
// 
// REORDERING ARRAYS
*/

Given two integer arrays of same size, “arr[]” and “index[]”, reorder elements in “arr[]” according to given index array. It is not allowed to given array arr’s length.

Example:

Input:  arr[]   = [10, 11, 12];
        index[] = [1, 0, 2];
Output: arr[]   = [11, 10, 12]
        index[] = [0,  1,  2] 

Input:  arr[]   = [50, 40, 70, 60, 90]
        index[] = [3,  0,  4,  1,  2]
Output: arr[]   = [40, 60, 90, 50, 70]
        index[] = [0,  1,  2,  3,   4] 
        
Expected time complexity O(n) and auxiliary space O(1)

We strongly recommend you to minimize your browser and try this yourself first.

A Simple Solution is to use an auxiliary array temp[] of same size as given arrays. Traverse the given array and put all elements at their correct place in temp[] using index[]. Finally copy temp[] to arr[] and set all values of index[i] as i.
//Java to find positions of zeroes flipping which
// produces maximum number of consecutive 1's
 
import java.util.Arrays;
 
class Test
{
    static int arr[] = new int[]{50, 40, 70, 60, 90};
    static int index[] = new int[]{3,  0,  4,  1,  2};
     
    // Method to reorder elements of arr[] according
    // to index[]
    static void reorder()
    {
        int temp[] = new int[arr.length];
      
        // arr[i] should be present at index[i] index
        for (int i=0; i<arr.length; i++)
            temp[index[i]] = arr[i];
      
        // Copy temp[] to arr[]
        for (int i=0; i<arr.length; i++)
        { 
           arr[i]   = temp[i];
           index[i] = i;
        }
    }
     
    // Driver method to test the above function
    public static void main(String[] args) 
    {
         
        reorder();
         
        System.out.println("Reordered array is: ");
        System.out.println(Arrays.toString(arr));
        System.out.println("Modified Index array is:");
        System.out.println(Arrays.toString(index));
         
    }
}
\*

----------------------------------------------------------------------------------------------------------------------------

public static void selectionSort (int arr[]}
{
for (int i=0; i< arr.length -1; i ++){
int index = i;
for (int j=i+q;j< arr.length; j++;)
{
if (arr[j] < arr[index]) {
index = j;
}
}
int smallerNumber = arr[index];
arr[index] = arr[i];
arr[i] = smallerNumber
