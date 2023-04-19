Leaner syntax than Java

C# primitives are objects due to being alias of .Net types which are objects, while in Java primitves are not, there you need to use a wrapper class
    in Java: Integer(wraps(int)), also only objects can be generic params:
        List<Integer> intlist .yes
        List<~~int~~> intlist .NO
    in C#: 
        List<Integer> intlist .yes
        List<int> intlist .yes

C# provides syntax for some feature, while Java accomplishes it via a class

In Java primitives are values types, classes are reference types, C# lets you choose the type (use ref, but also class is reference, struct is value by default)