# Unity Scripting - Getter and Setter Annotations

let's examine the code down below . 

```
using System;
using System.Collections;
using System.Collections.Generic;
using UnityEngine;

public class PlayerStats 
{
    private int _health; 
    public int Health{
        get {
            return _health;
        }
        set {
            _health = value;
        }
    }

    private int _power; 
    public int Power { get; set; }
    public string name;

    public PlayerStats(int health,int power , string name)
    {
        Health = health;
        this._power = power;
        this.name = name;
    }

    public void printPower()
    {
        Debug.Log(this._power);
        Debug.Log(this.Power);
    }


    public void Apply()
    {
        
        this.Power = 100; 
        this.printPower();
        

    }
}
```


<br>

- Getters and setters are used for manipulating/reading private fields of the class.
- Properties are the members that provide a flexible mechanism to read, write, or compute the value of a private field. In order to read or write a private field , properties use getters and setters. 
- There are two annotations that you can imply Properties in your code in c#. 
    1. Property that has a custom getter and setter
        ```
            private int _health; 
            public int Health{
                get {
                    return _health;
                }
                set {
                    _health = value;
                }
            }
        ```
    2. property annotation that makes another flag quickly. 
   
        ```
        public int Power { get; set; }
        ```

<br> 
<br>

- NOTE : Second annotation makes it's own flags. What I mean by that is this : 
    ```
    private int _power; 
    public int Power { get; set; }
    ```
    `_power` flag and the `Power` property that creates it's own flags are different. When you use the setter from the `Power` property, it wont affects the `_power` flag.

    ```
    public void printPower()
    {
        Debug.Log(this._power); // OUTPUT : 0
        Debug.Log(this.Power);  // OUTPUT : 100
    }


    public void Apply()
    {
        this.Power = 100; 
        this.printPower();
    }
    
    ```