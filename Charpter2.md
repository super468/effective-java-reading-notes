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