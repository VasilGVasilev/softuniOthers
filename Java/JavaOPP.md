Encapsulation in Java is private variables accessible only via getter and setter methods, in JS same is achieved via closures - access to variables defined in closure function via returned function that are bundled with their lexical environment, namely, variables.
    The function remembers the environment in which it was created;
    The general theme is this: we have access to variables defined in enclosing function(s) even after the enclosing function which defines these variables has returned;
    We know that an environment has access to its parent’s environment, and its parent environment has access to its parent environment, and so on. This set of identifiers that each environment has access to is called “scope.” We can nest scopes into a hierarchical chain of environments known as the “scope chain”;

Dynamic Scope vs. Static Scope in JS

    var x = 10;

    function foo() {
        var y = x + 5;
        return y;
    }
    
    function bar() {
        var x = 2;
        return foo();
    }
    
    function main() {
        foo(); // Static scope: 15; Dynamic scope: 15
        bar(); // Static scope: 15; Dynamic scope: 7
        return 0;
    }

    With static scope, the return value of bar is based on the value of x at the time of foo’s creation. This is because of the static and lexical structure of the source code, which results in x being 10 and the result being 15.

    Dynamic scope, on the other hand, gives us a stack of variable definitions tracked at runtime — such that which x we use depends on what exactly is in scope and has been defined dynamically at runtime. Running the function bar pushes x = 2 onto the top of the stack, making foo return 7.

Inheritance

The abstract keyword is a non-access modifier (public, private, protected are access modifiers), used for classes and methods:

    Abstract class: is a restricted class that cannot be used to create objects (to access it, it must be inherited from another class).

    Abstract method: can only be used in an abstract class, and it does not have a body. The body is provided by the subclass (inherited from).
        abstract class Animal {
            public abstract void animalSound();
            public void sleep() {
                System.out.println("Zzz");
            }
        }

Why use Interfaces to achieve greater abstraction? - Remember, a Java class can only have 1 superclass, but it can implement multiple interfaces. Thus, if a class already has a different superclass, it can implement an interface, but it cannot extend another abstract class. Therefore interfaces are a more flexible mechanism for exposing a common interface.