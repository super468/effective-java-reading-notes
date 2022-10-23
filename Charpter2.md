# Creating and Destroying  Objects
## Iterm 1: Consider static factory methods instead of constructors

try to create a instance by static factory methods instead of constructors like this below
```
public static Boolean valueOf(boolean b) {
    return b ? Boolean.TRUE : Boolean.FALSE;
}
```
it has multiple advantages
1. it can have meaningful names compared with constructor
2. static factory method are not required to return new objects each time they're invoked. You can reuse the objects when needed. Like Flyweight pattern
3. static factory method can return an object of any subtype of their return type
4. the class of the returned object can vary from call to call as a function of the input parameters
5. the class of the returned object need not exist when the class containing the method is writtern ?

Few limition of this
1. the class that provides only static factory method, without constructor can't be subclassed
2. they're hard for programmers to find. We need to have a better name convention like
    
    2.1 form/of/valueOf/getInstance/newInstance/getType/newType/type

Overall, we should should consider static factory method over constructor.

## Item 2: Consider a builder when faced with many constructor parameters

when you're creating an object with many optional parameters, try to use builder.
The builder pattern is well suited to class hierarchies.

## Item 3: Enforce the singleton property with a private constructor or an enum type

To implement singletons, you need to keep the constructor private and export a public static member to provide access to the sole instance.
1. It can be either a public final field.
    1. simple and clear
2. a public static factory method.
    1. change your mind about whether the class is a singleton
    2. can write a generic singleton factory
    3. a static factory is a method reference can be used as a supplier
3. declare a single element enum 

## Item 4: Enforce noninstantiability with a private constructor

a utility class can be made noninstantiable by including a private constructor
