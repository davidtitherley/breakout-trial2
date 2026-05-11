# Introduction
<div style="font-size:20px;">
In this tutorial we are going to make our own version of the Arcade Classic 'Breakout'
The aim of the game is to bounce the ball off a paddle to destroy all of the blocks. 

Click Next to Begin

## Step 1
We are going to begin by creating the bricks for our breakout game. 
Instead of creating a Sprite, we are going to create an array.
1. Click Advanced in the menu
2. Select the ``||arrays:arrays|`` menu and set list to array.
3. Drag into the on start block.
4. Select the drop down menu for list and creaate a new variable
2. Name it: brickColours
```blocks
let brickColours = [0. 1]
```

## Step 2
We will use the array to make rows of coloured blocks. 
There are 16 numbers used to represent colours in Makecode. 
We will use four of them. 
1. Click the plus sign in your array block and expand to four numbers. 
2. Name the numbers 2, 4, 5, 7
```blocks
let brickColours = [2, 4, 5, 7]
```


## Step 3
The next step is to set up a loop to create rows.
1. Go to ``||loops:loops|`` menu and drag out a ``||loops:for index from 0 to 3||`` block. 
2. Rename index to row.
```blocks
let brickColours = [2, 4, 5, 7]
for (let row = 0; row <= 3; row++) {
}
```
## Step 4
Now we are going to add another loop insode this for the columns. 
1. Go to ``||loops:loops|`` menu and drag out a ``||loops:for index from 0 to 3||`` block.
2. rename index to 'col' short for coloumn. 
3. Set the look from 0 to 7
```blocks
let brickColours = [2, 4, 5, 7]
for (let row = 0; row <= 3; row++) {
    for (let col = 0; col <=7; col++)}
}
```

## Step 5
Now we have a way to organise our bricks into columns and rows. Lets create the bricks. 
This section will be entirely in the row/column loops. 
1. Go to ``||variables:variables||`` and make a new variable called brickImage.
2. Select the Advanced menu. 
3. Go to ``||images:images||`` and drag a ``||image:image.create(width, height)||`` to replace 0 in your variable. 
4. Set the image width and height as:
width = 16
height = 6
```blocks
let brickImage: Image = null
for (let row = 0; row <= 3; row++) {
    for (let col = 0; col <= 7; col++) {
        brickImage = image.create(16, 6)
    }
}
```

## Step 6
1. From the ``||images:images||`` menu, drag a ``||images.image.fill(c)||`` block into the column loop. 
2. Change the variable name from picture to brickImage
3. From the ``||arrays:arrays||`` menu, drag a ``||arrays.list[0]||`` block to replace the grey colour.
4. create a new variable called colours. Select this in your get value block. 
5. replace get value at 0 with the variable row. You can find this block in the variables menu. 
```blocks
let brickImage: Image = null
let brickColours = [
2,
4,
5,
7
]
for (let row = 0; row <= 3; row++) {
    for (let col = 0; col <= 7; col++) {
        let colours: number[] = []
        brickImage = image.create(16, 6)
        brickImage.fill(colours[row])
    }
}
```

## Step 7
At this stage there is still nothing in our emulator screen. 
We are close to creating our bricks. Just a few more things to do. 
1. from the ``||sprites:sprites||`` menu, drag a ``||sprites.create(img, kind) block into the column loop.
2. Rename your sprite to a new variable called brick.
3. Make a new kind called Brick for your sprite. 
3. Replace the image square the variable brickImage from your variable list. 
```blocks
namespace SpriteKind {
    export const Bricks = SpriteKind.create()
}
let brick: Sprite = null
let brickImage: Image = null
let brickColours = [
2,
4,
5,
7
]
for (let row = 0; row <= 3; row++) {
    for (let col = 0; col <= 7; col++) {
        let colours: number[] = []
        brickImage = image.create(16, 6)
        brickImage.fill(colours[row])
        brick = sprites.create(brickImage, SpriteKind.Bricks)
    }
}
```

## Step 8
Our final step in creating the bricks is to set the x and y position of the bricks.
1. From the ``||sprites:sprites||`` menu, drag a ``||sprites:sprites.setPosition(x)||`` block into the loop. 
2. From the ``||Math:Math||`` menu, drag a ``||math:math.plus||`` block to replace 0
3. Add 20 to the first part of your plus block. 
4. In the second part of the plus block we are going to put in a multiply block from Maths. 
5. Drag the variable col into the first part of the multiplier. 
6. Add 18 to the second part of the multiplier. 

This will space out each of your blocks evenly on the row. 
```blocks
namespace SpriteKind {
    export const Bricks = SpriteKind.create()
}
let brick: Sprite = null
let brickImage: Image = null
let brickColours = [
2,
4,
5,
7
]
for (let row = 0; row <= 3; row++) {
    for (let col = 0; col <= 7; col++) {
        let colours: number[] = []
        brickImage = image.create(16, 6)
        brickImage.fill(colours[row])
        brick = sprites.create(brickImage, SpriteKind.Bricks)
        brick.x = 20 + col * 18
    }
}
```

## Step 9
The last part is to set the y position. We can do this easily by duplicating the x block. 
1. Right click on the set brick x block, and select duplicate. 
2. Change x to y. 
3. change column to row. 
4. change 18 to 10.
```blocks
namespace SpriteKind {
    export const Bricks = SpriteKind.create()
}
let brick: Sprite = null
let brickImage: Image = null
let brickColours = [
2,
4,
5,
7
]
for (let row = 0; row <= 3; row++) {
    for (let col = 0; col <= 7; col++) {
        let colours: number[] = []
        brickImage = image.create(16, 6)
        brickImage.fill(colours[row])
        brick = sprites.create(brickImage, SpriteKind.Bricks)
        brick.x = 20 + col * 18
        brick.y = 20 + col * 10
    }
}
```

## Complete
Check your screen. You should now have four rows of different coloured blocks. 
This is the end of the tutorial, you are now up to the next step. 

Going further
Try experimenting with your block colours by changing the array values in the brickColours variable. 
