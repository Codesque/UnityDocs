# Unity Scripting - Arrays , Lists and ArrayLists

## What is an Array ? 
- An array is a collection of similar data-types .
- Arrays are efficient if we are talking about performance. 
- Arrays shouldn't be used if we care about maintabilty.
- You can declare and then assign arrays to a variable with this 1 line of code : 
    ```
    int[] arr = new int[50];
    ```
- You can initialise an array like this : 
    ```
    int[] numbers = {   1,  2,  3,  4,  5  };
    ```
- Example of iterating through an array
  ```
  int[] numbers = { 1, 2, 3, 4, 5 };

  foreach(int num in numbers){
    Console.WriteLine(num);
  }
  ```

## What is a List ?
- A list is a collection of elements that can be different types of data. While the capacity of Arrays are determined , A list can change it's own capacity dynamically. 
- Multiple entries with the same data is considered different elements in list data structure.
- Lists are efficient if we are talking about maintabilty. 
- Lists shouldn't be used if we care about performance.
- Example of the Lists 
    ```
        public class PlayerInventory
        {
            private List<InventorySlot> inventory;
            PlayerInventory(int slotCount)
            {
                this.inventory = new List<InventorySlot>();
                for(int i = 0 ; i < slotCount ; i++) this.inventory.Add(new InventorySlot());
                Debug.Log("inventory has " + this.inventory.Count + " slots.\n");
            }

            void ClearInventory(){this.inventory.Clear();}
        }

    ```

## When should I use 'Arrays' rather than 'Lists' or 'Lists' rather then 'Arrays' ?

- It is recommended to use lists at the first place. Because as a software engineer you should consider maintablity rather than performance most of the time. 
- If the data that you are going to store has a limited capacity than you should consider using arrays rather than lists. 
    -   Because of the fact that you don't need to change the storage capacity of the data structure , you don't need the maintablity of the list. Using them just costs you some free space. 


 