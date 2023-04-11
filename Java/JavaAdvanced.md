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