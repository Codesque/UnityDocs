# Unity Basics - Sprite Sheets

## What is a sprite sheet ?
- A sprite sheet is a collection of sprites that creates an animation when the sprites are rendered in order. 
- Importing sprite animation frames as a sprite sheet is the best practice when we consider memory efficiency. 

## How to organise our components ? 
- You can organise your components with creating hierarchicy by creating folders and sub-folders. You can do that by : 
  1. Go to the `Project Tab --> Assets` 
  2. Right click and select the `Folder` option

## How to make unity render sprite-sheets as per sprite rather than the whole sheet ?
- You can do that by following the steps : 
    1. From assets folder select the sprite-sheet 
    2. From the inspector change the `Sprite Mode` option from Single to Multiple. 
    3. Click to the `Apply` button which is on the right corner . 
    4. From the `Sprite Mode` section , click to the `Sprite Editor` button. It will open the "Sprite Editor" tab .
    5. From the "Sprite Editor" tab choose the `Slice` sub-tab. You might change the slice type from `Automatic` to `Grid by cell size` if you know the pixel size of the animation frame. 
    6. After checking if the rectangles that surround the sprites normalise itself correctly , click on the `Apply` button which is on the right corner of the "Sprite Editor" tab. 

<br>

- Automatic slicing does a pretty good job most of the time. But when it fails, you can change the rectangle that determines the sprite's borders. 

