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
