# Unity Scripting - Abstractions And Interfaces in C# 

## What is an Abstract Method ? 
- An Abstract method doesn't have a body. 

    ```
    abstract class Language {

        // abstract method 
        public abstract void display1();

        // non-abstract method
        public void display2() {
            Console.WriteLine("Non abstract method");
        }
    }
    ```


## What is an Abstract Class ? 
- Abstract classes are the classes that are only used for inheritance purposes. Another words, You shouldn't make an instance of an abstract class. 
- An abstract class can have non-abstract methods.
    ```
    using System;
    namespace AbstractClass {

    abstract class Language {

        // non-abstract method
        public void display() {
        Console.WriteLine("Non abstract method");
        }
    }

    // inheriting from abstract class
    class Program : Language {

            static void Main (string [] args) {
            
            // object of Program class
            Program obj = new Program();

            // access method of an abstract class
            obj.display();

            Console.ReadLine();
            }
        }
    }
    ```

## What is Abstraction in OOP ? 
- Writing a solution with OOP is like creating a model of the problem, making the problem look easier, thus allowing to write good enough solutions.
But we don't need to model the whole thing down to the most minute details, because the model would be as complex as the problem itself. That would be like creating a map with a scale of 1:1. Such a map would be as big as the real thing.
We create a simplified model with the things that are crucial to the solution. Abstracting ourselves from the minutiae, not unlike a vehicle's suspension abstracts the driver from the unevenness of the road.
That's called generalization, or abstraction.

- Some of the benefits of abstraction : 
    - Reduce complexity. (Create a simple interface)
    - Allow for implementation to be modified without impacting its users.
    - Create a common interface to support polymorphism (treating all implementations of the abstracted layer the same.)
    - Force users to extend the implementation rather than modify.
    - Support cross platform by changing the implementation per platform. 


## What is interface in C# ? 
- Interfaces are like abstract classes. But unlike abstract classes , it is all made up by abstract methods.
- Unlike abstract classes, A class can implement multiple interfaces. 
- All the names of interfaces starts with capital 'I' to imply it is an interface. 
    ```
        using System;
            namespace CsharpInterface {

            interface IPolygon {
                // method without body
                void calculateArea(int a, int b);

            }

            interface IColor {

                void getColor();
            }
            
            // implements two interface
            class Rectangle : IPolygon, IColor {

                // implementation of IPolygon interface
                public void calculateArea(int a, int b) {

                int area = a * b;
                Console.WriteLine("Area of Rectangle: " + area);
                }

                // implementation of IColor interface
                public void getColor() {

                Console.WriteLine("Red Rectangle");
                        
                }
            }

            class Program {
                static void Main (string [] args) {

                Rectangle r1 = new Rectangle();
                
                r1.calculateArea(100, 200);
                r1.getColor();
                }
            }
        }
    ```

- Some of the benefits of interfaces : 
    -   Similar to abstract classes, interfaces help us to achieve abstraction in C#.

        Here, the method calculateArea() inside the interface, does not have a body. Thus, it hides the implementation details of the method.

    -   Interfaces provide specifications that a class (which implements it) must follow.

        In our previous example, we have used calculateArea() as a specification inside the interface IPolygon. This is like setting a rule that we should calculate the area of every polygon.

    -   Interfaces are used to achieve multiple inheritance in C#.


    -   Interfaces provide loose coupling(having no or least effect on other parts of code when we change one part of a code).
  
        Imagine we also have to model a square. Because of the abstraction we have made in the Rectangle class, manipulating the `calculateArea()` doesn't affect the Rectangle class. 

        ```
          class Square : IPolygon {

            // implementation of IPolygon interface
            public void calculateArea() {
            
                int l = 30;
                int area = l * l;
                Console.WriteLine("Area of Square: " + area);
            }
        }
        ```