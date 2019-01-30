# Midterm

As we have already said, arrays are capable of storing objects also. For example, we can create an array of Strings which is a reference type variable. However, using a String as a reference type to illustrate the concept of array of objects isn't too appropriate due to the immutability of String objects. Therefore, for this purpose, we will use a class Student containing a single instance variable marks. Following is the definition of this class. 

class Student {
   int marks;
}

An array of objects is created just like an array of primitive type data items in the following way. 

Student[] studentArray = new Student[7];

The above statement creates the array which can hold references to seven Student objects. It doesn't create the Student objects themselves. They have to be created separately using the constructor of the Student class. The studentArray contains seven memory spaces in which the address of seven Student objects may be stored. If we try to access the Student objects even before creating them, run time errors would occur. For instance, the following statement throws a NullPointerException during runtime which indicates that studentArray[0] isn't yet pointing to a Student object. 

studentArray[0].marks = 100;

The Student objects have to be instantiated using the constructor of the Student class and their references should be assigned to the array elements in the following way. 

studentArray[0] = new Student();

In this way, we create the other Student objects also. If each of the Student objects have to be created using a different constructor, we use a statement similar to the above several times. However, in this particular case, we may use a for loop since all Student objects are created with the same default constructor. 

for ( int i=0; i<studentArray.length; i++) {
studentArray[i]=new Student();
}

The above for loop creates seven Student objects and assigns their reference to the array elements. Now, a statement like the following would be valid. 

studentArray[0].marks=100;

Enhanced for loops find a better application here as we not only get the Student object but also we are capable of modifying it. This is because of the fact that Student is a reference type. Therefore the variable in the header of the enhanced for loop would be storing a reference to the Student object and not a copy of the Student object which was the case when primitive type variables like int were used as array elements. 

for ( Student x : studentArray ) {
    x.marks = s.nextInt(); // s is a Scanner object
}

Recall that we were not able to assign to the array elements in a similar way when the array was of type int. 

Moreover, in the case of array of objects, when we pass an array element to a method, the object is susceptible to changes. This is because the element being passed is also a reference type item. This differs from the situation when we have an int array. Following illustrates this concept. 

public static void main(String[] args) {
    Student[] studentArray = new Student[7];
    studentArray[0] = new Student();
    studentArray[0].marks = 99;
    System.out.println(studentArray[0].marks); // prints 99
    modify(studentArray[0]);
    System.out.println(studentArray[0].marks); // prints 100 and not 99
    // code
}

public static void modify(Student s) {
    s.marks = 100;
}

Compare the output with the one when the array was of type int[]. 

Processing an array of objects is much similar to the processing of an array of primitive type. the only thing to be kept in mind is the possibility of NullPointerException being thrown during run time and also remembering that the array elements themselves are reference types, which brings subtle differences from the case when they are passed as parameters. Moreover, an enhanced for loop may be used to initialise the array elements. 

Next : Multi dimensional arrays 
Prev : Searching and sorting arrays
