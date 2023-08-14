# Unity Scripting - Inheritance in C# 

## What are the types of inheritance ? 

The arrow that corresponds to some class is more primitive(base class) while the class that corresponds to the bottom of the arrow is more complex(derived class). 

-   Single inheritance
    <img src="https://www.programiz.com/sites/tutorial2program/files/csharp-inheritance.png">

-   Multilevel inheritance 
    <img src="https://www.programiz.com/sites/tutorial2program/files/csharp-multilevel-inheritance.png">

-   Hierarchical inheritance : All derived classes have the same , single ancestor. 
    
    <img src="https://www.programiz.com/sites/tutorial2program/files/hierarchical-inheritance-csharp.png">

-   Multiple Inheritance : If a derived class is derived by two or more ancestor classes , it's called Multiple Inheritance. 

    <img src="https://www.programiz.com/sites/tutorial2program/files/multiple-inheritance-csharp.png">

-   Hybrid Inheritance  : If two or more types of inheritance is used in a data structure, it's called Hybrid Inheritance.

    <img src="https://www.programiz.com/sites/tutorial2program/files/csharp-hybrid-inheritance.png">
    In this example , multilevel inheritance and multiple   inheritance are used at the same time.

# How to properly inherit from a class ? 

- You have to use the constructor of the ancestor class with parameters if you don't have the second constructor version which has no parameters. 
  ```
  public class Player {
        public Player(int health){
            this.health = health;
        } 

        // public Player(){} // Without this you will get an error while inheriting.
  }
  ```

  ```
  public class Warrior : Player{
    // You will have to use `Player(int health)` constructor to get rid of the error that is thrown in the `Warrior` keyword. 
  }
  ```



## What is this 'base' keyword ? 
-   The base keyword is equivalent to 'super' in Java (or Python). With this keyword you can override the method by using the old method. For an example : 
    ```
    class A {
        protected virtual void Foo() {
            Console.WriteLine("I'm A");
        }
    }

    class B : A {
        protected override void Foo() {
            Console.WriteLine("I'm B");
        }

        public void Bar() {
            Foo();
            base.Foo();
        }
    }


    public static void Main(String[] args){
        new B().Bar(); 
        // OUTPUT : I'm B \n I'm A

    }

    ```

## What is the 'virtual' keyword? 
- Virtual keyword is used for applying polymorphism in C#. Without the 'virtual' and 'override' keywords , If you override a method by hiding the method you will end up using the method which depends on the declared type of the instance.
    ```
    class A
    {
        public void Show() { Console.WriteLine("A"); }
    }

    class B : A
    {
        public void Show() { Console.WriteLine("B"); }
    }

    A a = new A();
    B b = new B();

    a.Show(); // "A"
    b.Show(); // "B"

    A a1 = b;
    a1.Show(); // "A"!!!
    ```

- In another word, if you "cast" a specialized version to the "base" version and call a method, always the specialised classes implementation will be used instead of the base version by using the 'virtual' keyword.

    ```
        class A
        {
            public virtual void Show() { 
                Console.WriteLine("A");
            }
        }

        class B : A
        {
            public override void Show() { 
                Console.WriteLine("B"); 
            }
        }


            A a = new A(); 
            B b = new B(); 

            a.Show();  // A 
            b.Show();  // B

            A a1 = b;  
            a1.Show(); // B

            B b1 = new B();
            b.Show();  // B 
    ```