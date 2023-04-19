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

Polymorphism
basic is about inheritance, but often with overriding or overloading, thus, the poly morphus thing 

Two types of polymorphism 
    Method overrriding (runtime) - the ability for a subclass to override a method allows a class to inherit from a superclass with 'near enough' actions and then change it as required. Overriding methods need to return the same type as the overridden method.
    Method overloading (compile) - one class having same named methods that accept different number of arguments

SOLID:
    single responsibility - each class should have only one responsibility
    open/closed - open for extensions, closed for modifications
    liskov substitution derived classes extend without replacing the functionality of old classes
    interface segregation
    dependency inversion - high level modules do not depend on low-level modules, both should depend on abstractions

Reflection - the ability of the programming language to be its own metalanguage
Annotations - @Override, @Deprecate

Tests are system, integration, unit

Design patterns types:
    Creational patterns - initialization and configuration of classes and objects
    Structural patterns - composition of classes and objects -> describe ways to assmeble objects to implement new functionality
    Behavioral patterns - deal with dynamic interactions among societies of classes -> distribute responsibility

see

https://medium.com/ssense-tech/dependency-injection-vs-dependency-inversion-vs-inversion-of-control-lets-set-the-record-straight-5dc818dc32d1

Article:

    Inversion of Control (IoC) is a design principle that refers to a way of designing software components to promote loose coupling and modularity. In IoC, the flow of control of a program is inverted, meaning that instead of a component controlling the flow of a program, it is managed by an external framework or container.

    In traditional programming, each component is responsible for controlling the flow of the program by calling other components and managing their behavior. With IoC, the framework or container manages the components, and the components are designed to respond to events or calls from the framework. This allows for greater flexibility and easier management of the program's behavior.

    IoC in React: 
        VDOM
            The Virtual DOM (VDOM) in React is an example of inversion of control because it shifts the responsibility of managing the actual DOM from the DEVELOPER to React. The VDOM is a lightweight representation of the actual DOM that is created and managed by React. When a component's state or props change, React compares the new VDOM with the previous VDOM and determines the minimum number of changes that need to be made to update the actual DOM. This means that the developer does not need to manage the DOM directly, and can instead focus on defining the behavior and structure of the components.
        Context API
            Another way that IoC is used in React is through the use of the context API. Context allows for the passing of data through the component tree without having to manually pass props down through each level. This allows for greater flexibility and easier management of data in the application.

    IoC is often implemented through the use of Dependency Injection (DI), which is a technique for providing the dependencies of a component from an external source rather than having the component create them itself. This enables the components to be easily swapped out and replaced without affecting the rest of the program's behavior. It separates the construction and configuration of services from its usage, relieving the dependent class from the former responsibility, decoupling it from its dependencies, and improving reusability and ease to test.