# OOP questions

## Software design

### Error handling

#### What does 'fail fast' mean in terms of exception handling? Why is it a good practice?
fail fast systems desing is basiclly, when we throw an exception instead of trying again or trying something else with a wrong value. It's a good practice, because we don't use more time and resource than we should use.

## Computer Science

### Data structures

#### How to find the middle element of singly linked list in O(n)?
We need to create a pointer, which is pointing to the head of the linked list and a field that counts the size of list. After that we need to iterate over the linked list, until the pointer reaches the end of the it, and with every step we add 1 to the counter field. We set the p to the head of the linked list again, but now we only go to the half of the counter field size (e.g.: 10/2) and then we can return the value of the pointer as a result.
#### Given an array of integers going from 1 to 100 (both inclusive) there is a duplicated entry. How to find it?
We need to create an integer variable (with the name like "currentNumber"), and then we check every number in the array with a for cycle ( for (int number : numbers)), and if number = currentNumber, then we return the number
#### What is a linked list? How to find if a linked list has a loop?
If we create a HashSet, we put the Nodes in it and we check them, if they are already in the collection or not. If they are, then it's a loop, if not then it isn't.
#### What is the Big O time complexity of the common operations in an ArrayList, LinkedList, HashMap? And of a bubble sort, quicksort, finding items in a Binary Search tree?
For the ArrayList and LinkedList it is O(n) (so it depends on the method we want to do with them, like 'get()' is O(1) but remove() is O(n) long)
For HashMap on the other hand, the O(1) is the average time of running.
#### How does HashMap work?
HashMap stores key-value pairs. Every pair is stored in a hash table, getting their index number based on the hashing algorithm that got applied (e.g.: Every character in the string has an ASCII code and with the sum of their ASCII character codes, we divide it with the size of the table and then we take the remainder as the index.).
#### Why is it important for keys in a map to have an immutable type? (Consider String for example.)
If we put a field String as a key for example, and then we modify it after we created the HashMap, then if we try to search the map for this key, it may not find a value as it's hashcode is changed and hashmap has calculated different index position for this key.

### Database

#### How can you connect your application to a database server? What are the possible ways?
JDBC, JPA
#### What do you know about database normalization?
Normalization is the process of organizing the data in the database. There are the four types of normal forms:

### Other

#### What is a garbage collector, in a nutshell?
Garbage collector is a system that can be found in programming languages like Java and C#. The garbage collector does what other need to do on the C language manualy, which is memory management. After a certain time, the garbage collector cleanes the memory from variables that we don't use anymore anymore in the program's runtime.

## Programming paradigms

### Procedural

#### What is casting? What is the difference between up vs downcasting?
Casting is when we convert a datatype into another datatype. Upcasting is the typecasting of a child to a parent object. Downcasting is basicly the same but in the other way.
#### Which order should we catch the exceptions? Why?
We need to catch the most specific exception first, then all the way to the most generic one, because we catch an exception, then it will be excecuted and the other will be ignored, so for example, if we create an exception for an Array and we generate a number generator, which can generate larger numbers than the Array's length and we use this number to get that index from the Array. We create an ArrayIndexOutOfBoundsException first, then we can handle this specific exception before a generic exception like RunTimeException.

### Object-oriented

#### What is a class?
Classes in Java are used as a blueprint for the object creation.
#### What is an object?
Objects (or instances) are members of a Class, with identity, behavior (method) and state (fields).
#### What is a constructor?
The constructor creates the instances from a Class. We can have more constructors for a Class, but it depends on the programmer and the usage of the Class.
#### Do we require parameter for constructors?
We don't have to give parameters to the constructor, unless we want to make the instances more unique.
#### What is an interface?
An interface is an abstract type that is used to specify a behavior that classes must implement. For example, I tell the interface, that if something implements it, the class must have a 'printHelloWorld' method, but I can't tell what will be the content of this method, I can only specify that it 
#### What are access modifiers?
Access modifiers specifies the accessibility of a field, method, constructor or class.
#### What is data hiding?
When you use private on field for example, so it can only be access via getters and setters, so no unauthorized access will be done on the field.
#### Can a static method use non-static members?
Static methods can't use non-static members.
#### What is the difference between hiding a static method and overriding an instance method?
In the first case, only the child class static method remains, but in the second case, both of the methods will be callable with their values.
#### Define the following terms: Instantiation, Attribute, Method
Instantiation: When you create an instance from a class via a constructor
Attribute: It's basically a field, but in an another term.
Method: A collection of statements, that perform a specific task, and it returns a result (if the return type is not a "void" of course) to the caller.
#### Could we access a static variable (or method) from a non-static method? Why?
We can, because a can only call non-static methods if we have an instance from the class where we can find it, so if we use a static method in it.
#### Could we access a non-static variable (or method) from a static method? Why?
We can't, because we don't need to instanciate a class to access a static method, but we use methods or field which are may be not instanciated.
#### How many instances you have of a static variable of a given class?
A static can't have more instances than 1.
#### Why is it not a good practice to write a lot of static methods?
Static methods remain in the memory for a log time and its garbage collection takes long time. Developer's don't have control on destroying or creating of Static variables. Excessive usage of static variables can result in the memory overflow.
#### What are the features of static attributes and static methods of a class? What are the benefits, when to use them?
The static can be used mainly for memory management reasons. If we don't want to create an object just so we can access a variable or field in it (like the PI variable for e.g.), then this can be a resons to create a static.
#### What is the ‘this’ reference?
The 'this' keyword refers to the current instance
#### What are base class, subclass and superclass?
Base class is a class, from which other classes are derived.
Superclass (or parent class) is the class from which a child class (or a subclass) inherits its constructors, methods, and attributes.
Subclass (or child class) is the class which inherits its constructors, methods, and attributes from a parent class.
#### Draw an object oriented family (as entities, with relations) on the whiteboard.
ok
#### Difference between overloading and overriding?
They are very different, the only thing common in them is that they both of them has a connection in a way with the methods.
Overloading: When you create more than 1 constructor on a method, and you give different type and number of arguments in it.
Overriding: When you "override" the original purpose of the method, and you do something unique with it.
#### What are the Object Oriented Principles? Explain the concepts with realistic examples!
Abstraction: Abstraction is that we “show” only essential attributes and we “hide” unnecessary information.
e.g.:We create a Car abstract class with the abstract void method accelerate. Then we create a Toyota class that extends Car and we put System.out.println("Toyota is going faster") in the accelerate method. And lastly in the main method, we create the Toyota instance and we call the accelerate method from it.
Encapsulation: No direct access to a class property fields should be allowed and we use public methods to access private fields and methods.
e.g.:We have a Dog class and it has a 'name', 'age' and 'gender' fields. We need to be sure that these fields are unreachable plainly, and we need to create getters and setters for this private fields.
Inheritance: A class (child class) can extend another class (parent class) by inheriting its features.
e.g.:If we create a Felidae class for felines and then we create a Cat class, then if we extend the Felidae class, then the Cat class will have all the features from the Felidae class.
Polymorphism: Allows us to perform the same action in many different ways
e.g.:We create a Felidae interface, a Cat class and a Lion class. The Felidae interface has a method called 'makeSound'. Both Cat and Lion inherits the Felidae interface, they have the same methods in their classes, but if we call this class methods, they are not the same, because they don't make the same sound. The Cat class will print "MEOW" and the Lion class will print "ROAR".
#### What is method overloading?
Overloading is when we make a constructor for example, and we make this constructor with different arguments. (like: class Dog(String name); class Dog(int size); class Dog(int size, String name))
#### What is method overriding?
Overriding is when we override the original functionality of the method, and we customize it to the case we use.
#### Explain how object oriented languages attempt to simplify memory management for Programmers.
Unlike the C language, Java (and C#) for example use an automatic garbage collection system, so unused variables get cleared from the memory.
#### Explain the “Single Responsibility” principle!
Classes can only be responsible for only 1 functionality (like we can't use our BoardGenerator class to calculate the steps in a chess game. We use the Game method for that.)
#### What is an object oriented program? Explain, show.
An object oriented program contains classes and instances from that class.
#### How do you make a class immutable? What do you need to watch out for?
We can use the 'final' keyword to do that (for example: final class Dog {}).
#### How many instances can be created for an abstract class?
You can't make instances from abstract classes.

## Programming languages

### Java

#### What is autoboxing and unboxing?
Autoboxing is the automatic conversion that the Java compiler makes between the primitive types and their corresponding object wrapper classes. For example, converting an int to an Integer, a double to a Double, and so on. If the conversion goes the other way, this is called unboxing.
#### If you have a variable, that shall store a positive whole number between 0 and 200, what primitive type would you use to store it?
short, because it can store numbers from -32,768 to 32,767.
#### What is the "golden rule" of variable scoping in Java? What is the lifetime of variables?
#### What is the purpose of the ‘equals()’ method?
The purpose of the 'equals()' is that we can compare two non-primitive elements (like Strings), because it compares the memory adress content and not the memory adresses.
#### What is the difference between '==' and 'equals()'?
Both equals() method and the == operator are used to compare two objects in Java and equals() method for content comparison. In simple words, == checks if both objects point to the same memory location whereas . equals() evaluates to the comparison of values in the objects.
#### What does the ‘static’ keyword mean?
Static means that the particular method/field belongs to a type itself, rather than to an instance of that type. So, the static method/field can be called even if you don't instantiate the class.
#### Why is the main() method declared as static? Explain.
The main() method is static so that JVM can invoke it without instantiating the class.
#### What is the default access modifier in a class?
The default access modifier is declared if a class has no modifier. It is visible only within its own package (directory)
#### What is the JVM?
Java Virtual Machine enables our Operating System (OS) to run Java programs or programs compiled into Java bytecodes.
#### What is the difference between the JRE and the JDK?
Java Development Kit (JDK) enables programers to work with the Java language and includes the JRE.
Java Runtime Enviroment (JRE) is used to run the Java programs, it has the java library and the JVM, but you can't write programs.
#### What is the difference between long and Long?
long: primitive type
Long: Object, can be null
#### Can a long store bigger numbers than a Long?
The long primitive can't store bigger numbers than the Long object. (-9,223,372,036,854,775,808 - 9,223,372,036,854,775,807)
#### What kind of packages do you know under java.util.* ? Bring at least 3 examples.
ArrayList, Arrays, List, Set
#### What are the access modifiers in Java? Which one could we use for class?
public, private, protected
#### Can an “enum” contain methods in Java? Explain.
If we put a curly bracket after every enum type, and write methods with the same name and then we create an abstract method under the enum types with the same name, then we can call the method on the enum type (e.g.: We have an enum Level, and we call the HIGH enum type and we want the method from it, then we call just call the method. Level.HIGH.printLevel() will be a void method with a System.out.println("HIGH"), so we get a "HIGH" in the console.
#### When would you use a private/protected/public attribute? What is the difference?
public: Other classes have access to the methods or field
private: Only the class has access to the method or field
protected: Only the the class and subclasses in the same package has access to the method or field
#### How do you prevent developers from subclassing a class?
If we use a final keyword on the class, then it can't be a subclass
#### How do you prevent developers from overriding a method in a subclass?
If we use a final keyword on the method, then it can't be overriden.
#### How do you prevent developers from changing the value of a variable?
We hide the variable with a 'private' access modifier and we don't create a setter for this variable.
#### Think about money ;) How would you store a currency value, that shall support decimal parts? Think it through again, and try to think outside of the box!
I would import java.math.BigDecimal and store the currency value in that, because it gives a more accurate result than double (e.g.: double: 0.03 - 0.02 = 0.0099... ; BigDecimal.: 0.03 - 0.02 = 0.01)
#### What happens if you try to call something, that you have no access to, because of data hiding?
if you use a 'private' access modifier, then an error stops the compiler, with the message: "'method or field' has private access in 'class'"
#### What happens if you try to delete/drop an item from an array, while you are iterating over it?
You can't delete an element from an array, you can only create a new array and exclude the elements you don't want.
The answert to the question is: It never happens, because you can't delete an array element.
#### What happens if you try to delete/drop/add an item from a List, while you are iterating over it?
You get an exception error, because for example, you want to iterate over a 5 element long Array, but you delete an element during the process, the loop will try to get the last element from the Array, but the it got less element than it had in the beginning, so we get an exception error.
#### What happens if you try to add an item to the end of an array, while you are iterating over it?
The last item will be ignored, because it is over the original size of the array.
#### If you need to access the iterator variable after a for loop, how would you do it?
I would save it in a new new variable, outside from the for loop's variable scope, because I can't use it outside the scope.
#### Which interfaces extend the Collection interface in Java. Which classes?
List, Set, SortedSet, NavigableSet, Queue, Deque
#### What is the connection between equals() and hashCode()? How are they used in HashMap?
hashCode() is used to calculate the bucket and therefore calculate the index. 
equals()is used to check that 2 objects are equal or not.
#### What is the difference between checked exceptions and unchecked exceptions? Could you bring example for each?
Checked exception is caught at compile time
#### What is Error in Java and how does it relate to Exception?
Exceptions and errors both are subclasses of Throwable class. The error indicates a problem that mainly occurs due to the lack of system resources and our application should not catch these types of problems. Exceptions are the problems which can occur at runtime and compile time.
#### When does 'finally' block run? What it is used for? Could you give an example from your projects when you would use 'finally'?
The 'finally' block always run, regardless of an exception occurred or not.
#### What is the largest number you can work with in Java?
2.147.483.647
#### When you use method overriding, can you change the access level of the method, from protected to public? Why?When you use method overriding, can you change the access level of the method, from public to protected? Why?
We can change the access level of the protected method to public, because we can place it into a bigger scope than it is, but we can't do it in the other way, because it is a lower level scope.
#### Can the main method be overridden? Explain your answer!
We can't override the main method, because the main method is static, and we can't override static methods.
#### When you use method overriding, can you throw fewer exceptions in the subclass than in the parent class? Why?
I can, because the complire let me do it.
#### When you use method overriding, can you throw more exceptions in the subclass than in the parent class? Why?
I can't, because the overidden method doesn't have that exception, so we will get a compile error.
#### What does "final" mean in case of a variable, method or a class?
'final' is used to give a variable a FINAL value, so it can't be modified anymore. We can declare a 'final' variable without a value, but whenever we give a value to it, we can't change it afterwards.
#### What is the super keyword?
The 'super' keyword' refers to the super class, where the object instanced from.
#### What are “generics”? When to use? Show examples.
Java Generics are a language feature that allows for definition and use of generic types and methods. We use them when we want to accept more types than one.
#### What is the benefit of having “generic” containers?
Because you can put anything into the place of the generic type.
#### Given two Java programs on two different machines. How can you communicate between the two? What are the possible ways?
Communication over a network involves two sockets, one on each of the computers involved in the communication. Java uses a class called java. net. Socket to represent sockets that are used for network communication.
#### What is an annotation? What can be annotated and how? Show examples.
Annotations are meta data. They don't affect the execution of the code. Annotations can be placed above classes, interfaces, methods, method parameters, fields and local variables.
e.g.:
@Override
we can override methods from superclasses. In this case, we override the public String toString() method. We can make the toString() method to do different things than before (like gives us back a String fields in one). We can't make the method to give us back a different type (like int) and we can't make it private, but we can rewrite the method content.

### C&#35;-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

#### Explain the purpose of IL and how does it relate to CLR?
#### What does “managed code” mean?
#### What is an assembly?
#### What is the difference between an EXE and a DLL?
#### What is the difference between `dotnet build` and `dotnet restore`?
#### What is strong-typing versus weak-typing? Which is preferred? Why?
#### What is a namespace?
#### Explain sealed class in C#?
#### What is explicit vs. implicit conversion? Give examples of both of them.
#### Is a struct stored on the heap or stack?
#### Can a struct have methods?
#### Can DateTimes be null?
#### List out the differences between Array and ArrayList in C#?
#### How is the using() pattern useful? What is IDisposable? How does it support deterministic finalization?
#### How can you make sure that objects using dedicated resources (database connection, files, hardware, OS handle, etc.) are released as early as possible?
#### Why to use keyword “const” in C#? Give an example.
#### What is the difference between “const” and “readonly” variables in C#?
#### What is a property in C#?
#### List out two different types of errors in C#?
#### What is the difference between “out” and “ref” parameters in C#?
#### Can we override private virtual method in C#?
#### What's the difference between IEquatable and just overriding Object.Equals()?
#### Explain the differences between public, protected, private and internal. Explain access modifier – “protected internal” in C#!
#### What’s the difference between using `override` and `new` keywords when defining method in child class?
#### Explain StringBuilder class in C#!
#### How we can sort the array elements in descending order in C#?
#### Can you use a value type as a generic type argument in C#? For example when implementing an interface like (IEquatable).
#### What are Nullable Types in C#?
#### Conceptually, what is the difference between early-binding and late-binding?
#### What is delegate, event, callback, multicast delegate?
#### What is enum in C#?
#### What is null-conditional operator?
#### What is null-coalescing operator?
#### What is serialization?
#### What is the difference between Finalize() and Dispose() methods?
#### How do you inherit a class from another class in C#?
#### What is difference between “is” and “as” operators in C#?
#### What are indexers in C# .NET?
#### What is the difference between returning IQueryable<T> vs. IEnumerable<T>?
#### What is LINQ? Explain the idea of extension methods.
#### What are the advantages and disadvantages of lazy loading?
#### How to use of “yield” keyword? Mention at least one practical scenario where it can be used?
#### What are attributes in C#? Give some examples of usage of them.
#### By what mechanism does NUnit know what methods to test?
#### What is the GAC? What problem does it solve?
#### What is the largest number you can work with in C#?
