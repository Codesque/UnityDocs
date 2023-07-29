# Unity Basics - Coroutines

## What is this "Coroutine" used for ? 

- Coroutines used for spreading tasks across several frames. In most situations , when you call a function within the `Update()` method , the function should be executed within the time of 1 changing frame. If we need to spread the task within multiple frames , we can use coroutines. 
- Coroutines aren't threads. Synchronous operations within the coroutine will be executed on the main thread. 
- It is the best practiCe to use Coroutines for asynchronous operations such as : 
    1.  HTTP transfers 
    2.  Asset Loads 
    3.  File I/O (Streaming) 
- Also Coroutines can be used for procedural animations. 

## How to use Coroutines in our Game Scripts ? 
- First of all , all the coroutines must return the type of IEnumerator object. 

  ```
  IEnumerator MyCoroutineMethod() {  
   // Your code here...  
     
   yield return null;  
  } 
  ```


- Secondly yield expression is responsible for stopping the script and resuming the execution of the operation that is made within the Coroutine Method. There are plenty of `yield return` types that you can use in your coroutine.
    - `yield return null` will resume the execution after all the `Update()` functions have been called. 
    - `yield return new WaitForSeconds(t)` will resume the execution after approximately t seconds. 
    - `yield return new WaitForSecondsRealtime(t)` will resume the execution after approximately unscaled t seconds.
    - `yield return new WaitUntil(bool condition)` will resume the execution after the `condition` is met. 
    - `yield return new WaitWhile(bool condition)` will resume the execution after the `condition` is not met.
    - `yield return new WaitForEndOfTheFrame()` will resume the execution after all the cameras and the GUI have been rendered. 
    - `yield return new WaitForFixedUpdate()` will resume the execution after all the `FixedUpdate()` functions have been called.
    - `yield return new WWW(url)` will resume the execution after the web source at URL was downloaded or failed.
  
<br>
<br>

- In order to activate the Coroutine Methods , you need to use `StartCoroutine(string functionName)` or `StartCoroutine(IEnumerator function)` within the `Update()` or `Start()` methods of the game script.
- You can stop the coroutines by calling `StopCoroutine(string functionName)` or `StopCoroutine(IEnumerator function)`.

# COROUTINE EXAMPLE :

```
using System.Collections;  
using System.Collections.Generic;  
using UnityEngine;  
  
public class ColorChanger : MonoBehaviour  
{  
      
    private SpriteRenderer sr;  
    
    public Color color1;  
    public Color color2;  
    
    void Start () {  
        sr = GetComponent<SpriteRenderer>();  
        StartCoroutine(ChangeColor());  
    }  
    
    IEnumerator ChangeColor() {  
        
        while (true) {  
                
            if (sr.color == color1)  
                sr.color = color2;  
                
            else  
                sr.color = color1;  
                
            yield return new WaitForSeconds(3);  
        }  
    }  
} 


```