[![Review Assignment Due Date](https://classroom.github.com/assets/deadline-readme-button-22041afd0340ce965d47ae6ef1cefeee28c7c493a6346c4f15d667ab976d596c.svg)](https://classroom.github.com/a/7TXVPuTD)

## Author: Mehmet Furkan Yiğit
## HW 1
## This repository is cloned, it's questions have been answered and pushed for "Homework 1" questions asked

Q1: Why we need to use OOP? Some major OOP languages? 

-> Answer: We use OOP for modular, reusable and scalable applications. Abstraction, Polymorphism, 
            Encapsulation and Inheritance are the keys of this approach. 
            OOP allows us that creating things which has common features, 
            also preventing duplicate codes, simplifying complexity by modeling in real life (via Abstraction).

            Java, C++, C# and Python are the major examples of OOP languages.

Q2: Interface vs Abstract class?

-> Answer: Abstract classes can have abstract and concrete methods. 
            Inheritance is provided via the keyword "extends".
            It can have normal and "static final" variables.
            Also, public, protected and private access modifiers is acceptable.
            It is used for creating classes that have common feature or behaviour. (extends Animal, Car etc.)
            **is-a relationship**

            
            Interface is a structure that it's all methods are public abstract.
            Before Java 8, it could have only abstract methods. After Java 8, it can also have default and static methods.
            All variables are "public static final".
            It is used for defining the behaviours. (implements Flyable, Walkable etc.)
            **can-do relationship**

            A class can extend only one class. But it can implement more than one class.

Q3: Why do we need "equals" and "hashcode"? When to override?

-> Answer: Purpose of "equals" method is to use the reference equality, in the other words; it checks both objects refer to the same memory address.
            Override can be applied to define the conditions to accept equality.

            Hashcode generates an integer used by hash based collections to store or get objects fast.

            hashcode() with equals():
                if two objects are equal with equals(), then hashcode() values must be the same.
                if not, then hashcode() values can be different. (not a must)
            
            The time when to override is contract violation:
                if equals() is overrided and hashcode() is not, then both equal objects can generate different hash codes.
                    In this scenario, things can fail such as HashMap and HashSet.
            

            Performance Problems: Weak implementations may cause hash conflicts. In this situation, O(1) processes turns into O(n). (Linked List Traversal)

            Keys of success:
                Override both if needed.
                Do not use mutable fields.
                Use "Objects" utility.
            

Q4: Diamond Problem in Java? How to fix it?

-> Answer:  Diamond Problem is the situation that one class accesses the same method or property in two different ways, and can't decide which one to use.
            
            This problem can be fixed by overriding the method in class, calling the exact method (ClassB.super.save())
            Java solves this problem in compile time.

            So, it's easy to handle in Java.

            
Q5: Why we need Garbage Collector? How does it run?

-> Answer:  Garbage Collector optimizes memory management by preventing memory leaks, by removing malloc/free or new/delete loops and by deleting unused objects.

            Memory Allocation:
                In Java, heap is divided into generations;
                    Young Generation is for short-lived objects such as temporary variables.
                    Old Generation is for long-lived objects such as GC cycles.
            
            Identifying Garbage:
                Roots: Starting points like static fields, active thread stacks, JNI.
                Marking: Traverses all objects reachable from roots, marking them as alive.
                Unreachable objects: Anything not marked is considered as garbage.

            Different algorithms can be applied for cases; 
                It marks live objects, sweeps dead ones.
                Java's default:    Focuses on young generation. (most objects die young.)
                Divides heap into regions, prioritizes garbage-heavy areas.
                Uses concurrent threads to minimize pauses.

Q6: Java "static" keyword usage? 

-> Answer: Static keyword is used for a class variable, or a method, or defining a block.
            
            1- Class variable: 
                class Flower{
                    static int leafAmount=1;
                    Flower(){}
                    Flower flower = new Flower();
                    flower.leafAmount=4
                    }
            **value of a static variable changes on every object when it changes.**

                    int x = Flower.leafAmount;
            **also it can be called directly without creating an instance of a class.**
            
            2- Method: 
                class Flower{
                    static int getItself(int num){
                        return num;
                    }
                }
                Flower.getItself(1);

            3- Block: 
                static{
                    url = "http://www.123deneme.com"
                }
            **and also can be used in nested class scenarios.**

            ***In addition, it is also efficient with Singleton Design Pattern.***

            **It is stored in method area instead of heap.**

        Advantages of "static" keyword;
            1- It saves memory.
            2- More efficient in classes that includes utility methods.

        Disadvantages;
            1- It can corrupt the logic of OOP.
            2- object references like "this" and "super" cannot be used in static methods.


Q7: Immutability means? Where, How and Why to use it? 

-> Answer: Immutability means an object's state can't be changed after it's created.
            For changing the state, new object must be created with the updated value instead of modifying.

            Use cases:
                Thread-safety: Thanks to it's not able to be modified, it is safe for concurrent access in multi threaded apps.
                Predictability: Objects will remain consistent in their life cycle, and will prevent unexpected side effects.
                Caching: Immutable objects can be reused, reducing memory overhead.

Q8: Composition and Aggregation means and differences? 

-> Answer: Composition and Aggregation define "has-a" relationships between objects but differ in ownership and lifecycle dependency.

            In composition: 
                One object can't exist without the other one.
                If the owner is deleted, the contained object is also deleted.
                For example; there is a composition with human and heart. (A heart can't exist separately from a human)

            In aggregation:
                Objects can exist independently.
                Owner doesn't control the life cycle. 
                For example; library and books 

            Summary: Parent owns the child, child can't exist without it in composition.
                        Child can exist independently of the parent in aggregation.

Q9: Cohesion and Coupling means and differences? 

-> Answer: Cohesion tells us how well the elements within a module work together for a purpose. 
            High cohesion is better.
            Easy to maintain and understand when its high.

            Example: calling another service's methods without an interface or abstraction.


            Coupling means the degree of dependency between modules.
            Low coupling is better.

            Example: Interface & Dependency Injection should be used.

Q10: Heap and Stack means and differences? 

-> Answer: Heap is slower than stack. 
            Heap needs garbage collection. 
            

            Stack has fast access structure with LIFO.
            References the objects stored in the heap.
            Memory is automatically managed.
            StackOverflowError may be shown because of limited sizing.

Q11: Exception means? Type of Exceptions? 

-> Answer:  Exception is used for defining unexpected actions or events. 

            There are 3 types of exceptions:
                Compile time exceptions
                Runtime exceptions
                System-level errors

        Compile-time;
            IOException
            ModuleNotFoundException
        
        Runtime;
            NullPointerException
            OutOfBoundsException

        System-level;
            StackOverflowError
            OutOfMemoryError


Q12: How to summarize "clean code" as short as possible? 

-> Answer: If a code doesn't contain unused or unnecessary or duplicate parts and also easy to understand, then I can say that it's a clean code.

Q13: What is the method of hiding in Java? 

-> Answer: It occurs when a static method in a subclass has the same signature as a static method in its superclass.
            Only static methods can be hidden and not instances.
            The method in subclass doesnt override the superclass method, it hides.


Q14: What is the difference between abstraction and polymorphism in Java? 

-> Answer: Writing code within the main rules without going into details is abstraction. 
            Polymorphism is providing flexibility and making a behavior that can exhibit differences from object to object.
            

