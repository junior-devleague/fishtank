# fishtank

Build your own fish tank.

![Example](https://github.com/junior-devleague/fishtank/blob/master/example.gif)

## Objective

Use **DOM**, **CSS Positioning**, **If Statements**, **Events** and more to build a fish tank with a fish that follows your cursor.

## Prerequisites

To complete this project, students should have the following:
* Intermediate understanding of HTML elements (divs, images, attributes, structure...etc.)
* Intermediate understanding of CSS (Flexbox, absolute positioning...etc.)
* Intermediate understanding of JS (DOM, Events, variables, if statements, arrays)

## Your Challenge

### Part I

To complete Part I, fulfill the following requirements:

1. Clone this repository.
2. Create these additional files in your newly cloned fishtank folder:
  * index.html
  * styles.css
  * app.js
3. Link your files.

### Part II HTML

To complete Part II, fulfill the following requirements:
1. Create a ```div``` with an ```id``` of "container"
2. Inside of this container div, create an ```img``` with the source to "right1.png". This is the image of a fish facing to the right. Create additional ```img``` elements with paths to the rocks or other fishtank decor of your choice.
  * For each image, give it an id
  * For each image, give it a class of "item"

### Part III CSS

To complete Part III, fulfill the following requirements:
1. Target the ```body``` element.
  * Set the margin to 0px.
2. Target the ```id``` of "container".
  * Set the width to 100%
  * Set the height to ```calc(100vh)```
  * Set the background color to a shade of blue (for the water in the tank)
3. Target the ```class``` of "item".
  * Set the position to absolute
4. Target the id of your fish.
  * Set its width to 150px (Note: If you leave the height blank, it will automatically scale to be proportional to the width)
5. Target the id of your other images
  * Change the width or height as needed
  * Change the position of the element using top, left, bottom, right. Example:

``` css
#rock1 {
  width: 500px;
  bottom: 0px;  => 0 pixels AWAY from the bottom
  left: 300px;  => 300 pixels AWAY from the left
}
```
  * Use the z-index property if you want to control which elements are on top of eachother. Resource: https://www.w3schools.com/cssref/pr_pos_z-index.asp

### Part IV JS

To complete Part IV, fulfill the following requirements:
1. Start your file by making a function that will run your code when the window loads as follows:
``` javascript
window.onload = function() {
  // REST OF YOUR CODE IN HERE
}
```
2. In this onload function, create the following variables:
  * Variable to store your fish image element
  * Variable called "arrX" to store an empty array
3. Have your window listen for a mousemove event. Take in the ```event``` as a parameter for your function. The ```event``` is a special word that holds information about what happened during the event (mousemove) that the element is listening for. Here is one way to do this:

``` javascript
window.onmousemove = function(event) {
  console.log("The mouse has moved!");
}
```

4. In your mousemove function, do the following:
  * Create a variable called "x" that will store the X coordinates of our cursor. This can be done as follows:

``` javascript
window.onmousemove = function(event) {
  var x = event.clientX;
}
```
  * Using this pattern, create a variable called "y" that will store the Y coordinates of our cursor.

  * When we move our mouse, we want the position of our fish element to have the same X and Y coordinates of our cursor. Which CSS properties will allow us to set the fish image to the position of our cursor?
    * To change CSS in JavaScript, you can use this pattern: element.style.property = "value";

  * Change the fish image to face left when our cursor goes left and change the fish image to face right when our cursor moves right.
    * When our cursor moves right, its X coordinate INCREASES. When our cursor moves left, its X coordinate DECREASES.
    * How can we use arrays to help us detect when the X coordinate is increasing or decreasing?
    * We can push our X coordinates into an array!
    * Let's say we move our cursor to the right. Initially, the X coordinate is 300 (for example). The next coordinate is then 301 (because we are moving to the right and x values get larger when we move to the right). If we push this into an array, arr[0] = 300, and arr[1] = 301.  
      * Push the x value into arrX
      * Create an if statement that checks if there are more than 2 elements in the array
      * If so, remove the first element in the array (this makes it so that we only have 2 elements in the array at all times!)
      * Create another if statement that checks if the X coordinate is increasing:
        * If so, change the fish image to the right facing one
      * Create an if statement that checks if the X coordinate is decreasing:
        * If so, change the fish image to the left facing one

## Stretch Goals

1. 2 images for the right face and 2 images for the left face are provided. How could you alternate between the two images as you move your cursor so that it appears that the fish is actually swishing its tail and swimming?
2. Fishes can't predict your movements before they see it! Create a delay that allows your fish to be more lifelike and follow your cursor after you move it.
3. Create a group of fishes that follow your cursor!
