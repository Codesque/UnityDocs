# Unity Basics - RigidBodies and Colliders 

Having a rigid body component on a gameobject provide us that <b>the gameobject can interact with other resources of forces.</b> For an example , The gravity force is applied to all game objects that has a rigid body component. 

In order to remove a component , press the vertical three dots that besides of the component we want to delete. And then select `Remove Component` option.

## How to add a rigid body component to a gameobject ? 

- You can do that by pressing the `Add Component` button from the Inspector Tab which is in the bottom-mid and then use the search bar to find `RigidBody2D` component.(Don't select `RigidBody` because it is for 3D games.) 

## How to add a collider component to a gameobject ? 

- You can add it with the same way that you did with rigidbodies but also there are plenty of different options available.

    - If your sprite is a cubic you probably should add a `Box Collider 2D` component.
    - If your sprite is in a circular shape you should add a `Circle Collider 2D`

- When two colliders attached to each other without the `Is Trigger` option , The gravity force stops dragging the object to the bottom . 
- Trigger Colliders can detect collisions but this kind of collider can pass through other colliders. When you want to use a collider that dont apply the bounce effect to other colliders , you  will be likely to use the Trigger Colliders. 

 

