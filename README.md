interface Pet{
  public void test();
}
class Dog implements Pet{
   public void test(){
     System.out.println("Interface Method Implemented");
  }
   public static void main(String args[]){
     Pet p = new Dog();
     p.test();
  }
}


/// Main Class
package com.company;

    public class Main implements Pet{

        public void test(){
            System.out.println("Interface Method Implemented");
        }

        public static void main(String args[]){
            Pet p = new Main();
            p.test();

        }
    }


// Interface Class 
package com.company;

/**
 * Created by 13549lac on 18/12/2018.
 */
 interface Pet{
    public void test();
}


////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////

public interface SomeInterface{
   // constant declarations, if any
   // method signatures   
   int someMethod(String someString,
                              double someDouble,
                              int someInt);
                    double speedOfCar);
         ......
}
Note: that the method signatures have no braces and are terminated with a semicolon.

---------------------------

o use an interface, you write a class that implements the interface. When an instantiable class implements an interface, it provides a method body for each of the methods declared in the interface. For example,
public class myVersionOfSomeInterface implements SomeInterface {

    Int someMethod (String someString, 
                             double someDouble, 
                             int someInt) {
       // code for someMethod    }
………..
}



