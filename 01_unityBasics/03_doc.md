# Unity Basics - Moving character with Game Scripts 

```
using System.Collections;
using System.Collections.Generic;
using UnityEngine;

public class PlayerMovement : MonoBehaviour
{
    public float speed = 5f;
    
    // Update is called once per frame
    void Update()
    {
        float h = Input.GetAxis("Horizontal"); 
        float v = Input.GetAxis("Vertical");

        Vector2 pos = transform.position;
        pos.x += h * speed * Time.deltaTime;
        pos.y += v * speed * Time.deltaTime;


        transform.position = pos;
    }
}
```

- `Input.GetAxis(string Q)` gives us how character should move according to the input we gave to unity by the specified "Q" axis.
- when assigning `pos = transform.position` the value we get from `transform.position` is not referencing the actual address of the instance. Instead by doing that we are referencing the value which is taken from the actual address.(pass by value) . Because of that , when you make some operations to that `pos` variable make sure you `transform.position = pos` at the end. 
  
