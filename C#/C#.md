Leaner syntax than Java

C# primitives are objects due to being alias of .Net types which are objects, while in Java primitves are not, there you need to use a wrapper class
    in Java: Integer(wraps(int)), also only objects can be generic params:
        List<Integer> intlist .yes
        List<~~int~~> intlist .NO
    in C#: 
        List<Integer> intlist .yes
        List<int> intlist .yes