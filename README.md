# Understanding jQuery - Paint

This project aims to make you understand the basic DOM manipulation by creating program! A bit like Microsoft Paint.

Our `index.html` file 5400 divs in the house. Divs are small black square. These squares represent each pixel of our program. We did not preoccupy the HTML & CSS. Just our file named app.js

Step # 1 - Add Class

The first thing to do in our "pixels" is to change the color. These little guys are the building blocks of our artwork. With v1 our application, we'll just make black and white pixels. Not because we can not have colors, but we will need to create a few features for v2?

- Initialize our file `app.js` by loading the document when it is ready.

```Javascript
  $ (Document) .ready (function () {
  // your code
  })
```

All your code will be between these lines of code.

- Ensure that when you click on a pixel, it becomes white
  - In our index.html each div has class 'box'
  - We can use this class "box" as our selector. This gives us a way to interact with your DOM

```Javascript
  $ ( '. Box'). It ( 'click', function () {
    $ ( 'Box.') AddClass ( 'white').
  })

```

Our style.css file a class called white. Everything she does is to change the background from black to white boxes.

In theory, it would change the black box to click white box, but what's happening when you try?
It seems that when you click on a box, all our boxes are changed into white!

Indeed, they all share the same class with the name of the box. We are saying to jQuery that everything which refers to the class "box" should also be "white" class. This is a common problem in jQuery. Now we could give each div in the list of all 5400 div their own unique ID, but I have a better idea.

- Use the 'this' keyword

```Javascript
  $ ( '. Box'). It ( 'click', function () {
    $ (This) .addClass ( 'white');
  })
```

The keyword 'this' s really common in JavaScript, and it can be confused. In this case, our jQuery code, it refers to the specific case on which we clicked. Often you find yourself in positions where you need to change something in a picture of many. If you ever find yourself in changing each of them, experiment with 'this' a little.

## Step 2 - Edits

Great, now we can create beautiful works of art. art black and white, but art nonetheless. But what happens when we make a mistake? There is no way to change our work. We'll fix that.

- Ensure that when you double click, it changes back to black with `removeclass`

```Javascript
  $ ( '. Box'). It ( 'click', function () {
    $ (This) .addClass ( 'white');
  })

  $ ( '. Box'). One ( 'dblclick', function () {
    $ (This) .removeClass ( 'white');
  })
```

## Step 3 - Reset Button

It seems we have a reset button. Let it run. Remember how we could send blanket orders on all our pixels using the class name instead of individual pixel? We will use this method to create our reset button.

- Be on your button

```Javascript
  $ ( '# Reset'). It ( 'click', function () {
    $ ( '. Box'). RemoveClass ( 'white')
  })
```

## Step 4 - Color Pallette

Let our color buttons work!

- Create a color variable, and set the default blank. This color variable is the class we add.

```Javascript
  var color = 'white'
```

- Create a click event for each color that changes color variable when clicking

```Javascript
  $ ( '# Red'). It ( 'click', function () {
    color = 'red';
  })

  $ ( '# Blue'). It ( 'click', function () {
    color = 'blue';
  })

  $ ( '# Green'). It ( 'click', function () {
    color = 'green';
  })

  $ ( '# Yellow'). It ( 'click', function () {
    color = 'yellow';
  })

  $ ( '# White'). It ( 'click', function () {
    color = 'white';
  })
```

- Update the add-class functionality to reflect our color variable rather than our actual class names

```Javascript

  $ ( '. Box'). It ( 'click', function () {
    $ (This) .addClass (color);
  })

  $ ( '. Box'). One ( 'dblclick', function () {
    $ (This) .removeClass (color);
  })

  $ ( '# Reset'). It ( 'click', function () {
    $ ( '. Box'). RemoveClass (color)
  })

```

One last thing that is a little messed up. Our reset functions and double-click does not work yet. Because we set the "color" variable instead of the action of class suppression, it will only observe the currently selected color.

In the jQuery function we have the ability to delete multiple classes of only separating each class, we want to remove by a space, as follows:

```Javascript

  $ ( 'Box.') RemoveClass ( 'red blue green yellow white.');

```

What is feasible, but we'll just put those in a variable so that we do not need to write much code

```Javascript

  var colors = 'white blue green red yellow'

  $ ( '. Box'). One ( 'dblclick', function () {
    $ (This) .removeClass (colors);
  })

  $ ( '# Reset'). It ( 'click', function () {
    $ ( '. Box'). RemoveClass (colors)
  })

```
And now it's over, we finished our setup application. Feel free to add functionality. Enjoy!

## Copyright

© D. Rodolpe for Simplon.co, 2016.
