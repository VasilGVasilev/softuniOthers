Stack and queues use specific Java Element ArrayDeque

Arrays are two separate instances, fixed lenght any element and variable lenght but only objects

Lambda is an Java name for an anonymous function 
    (n) -> { System.out.println(n); }

A constructor in Java is a special method that is used to initialize objects. 
    // Create a Main class
    public class Main {
        int x;  // Create a class attribute

    // Create a class constructor for the Main class
    public Main() {
        x = 5;  // Set the initial value for the class attribute x
    }

    public static void main(String[] args) {
            Main myObj = new Main(); // Create an object of class Main (This will call the constructor)
            System.out.println(myObj.x); // Print the value of x
        }
    }
    Purpose: when we create a 'new' instance of the object, the user usually passes in some values -> the constructor makes connects that setting of values with initiation of the object via the class template:

        public class Person {
            private String name;
            
            public Person(String name) {
                this.name = name;
            }
            
            public String getName() {
                return name;
            }
            

        }

        Person person = new Person("John Smith");

        person = {name: "John Smith"}

    NB: constructor is thus necessary in class based inheritance, while in JS prototype based inheritance, we constructors are not necessary for object creation

Generics means parameterized types. The idea is to allow type (Integer, String, … etc., and user-defined types) to be a parameter to methods, classes, and interfaces.
    public class Box<T> {
        private T contents;
        
        public void set(T contents) {
            this.contents = contents;
        }
        
        public T get() {
            return contents;
        }
    }
Here, the Box class is defined as a generic class with a type parameter T. You can use any valid Java identifier in place of T, such as E, K, V, or any other meaningful identifier that helps you understand the purpose of the type parameter.

Purpose: instead of having same code for ,for example, three types - int, double, string, we make a generic, namely, instead of making class for int and all others, we make a generic class:
    public class Printer {
        Integer thintToPrint;
        
        public IntegerPrinter(Integer thingToPrint){
            this.thingToPrint = thingToPrint;
        }

        public void print() {
            System.out.printIn(thingToPrint);
        }
    }
    ->
    public class Printer <T> {
        T thintToPrint;
        
        public IntegerPrinter(T thingToPrint){
            this.thingToPrint = thingToPrint;
        }

        public void print() {
            System.out.printIn(thingToPrint);
        }
    }

    and when we actually initialize, we set the actual type:

    Printer<Integer> printer = new Printer(23);
    printer.print()

    
https://www.youtube.com/watch?v=K1iu1kXkVoA - Generics In Java - Full Simple Tutorial