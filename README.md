# GameMaker Studio 2 First Look

## Introduction
This tutorial is intended for those wanting an introducton to __GameMaker Studio 2__ using their scrpting language __GML__. This assumes no prior knowledge of the software or scripting. Unlike other tutorials, I have left the scripting in images so you can't cut and paste the text. When learning to script for the first time I think it is very important to type it in yourself and get used to making mistakes and develop an understanding of what you are typing does to the game engine.
  

This is a primer before moving forward and creating your first game.  It is intended to demonstrate some fundamental concepts in the __IDE__, __GML__, and some very basic __game algorithms__.  

Includes:

* Variables
* 3 Data types
* Functions
* If statements
* Loops
* Positioning objects in rooms
* Errors
* Moving NPC
* Moving Player

## Programming Concepts
The following programming concepts are raised in FirstLook.yyp.


| Programming Concept  | Description                                                                                                                                                                                                                                                                                                                                           | Example                                                                                                    |
|----------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------|
| Constants            | This is a value of a type that never changes                                                                                                                                                                                                                                                                                                          | `vk_up`                                                                                                      |
| Real Number          | This is a type that represents any whole number  and is a double precision floating point value                                                                                                                                                                                                                                                       | `-25.5`                                                                                                      |
| String               | This is a type that represents any text and is surrounded by quotation marks                                                                                                                                                                                                                                                                          | `"This is a sentence"`                                                                                       |
| Boolean              | This is a type that represents either true or false.   GML does not have a boolean type and uses a real number  to represent true and false.  Any real number below 0.5 is false and any  number equal or above is true.                                                                                                                              | `b_is_visible = true`                                                                                        |
| Variable             | A variable can store either a real number or a string. When the game  runs the variable is replaced with the value that it contains.  You assign a variable using the equal sign `=`.                                                                                                                                                                 | `speed = 20;`                                                                                                |
| Variable Definitions | This is a way that you can initialize the value of a variable both inside the game object (just under the Physics button) and allows you to give different values inside the room.                                                                                                                                                                    |                                                                                                            |
| String Concatenation | When adding two strings together "Hello " + "there." it combines (concatenates)  the two strings into a single "Hello there".                                                                                                                                                                                                                         | `"Hello " + "Steve!"`                                                                                        |
| if statement         | A simple "if" statement takes this form: if (condition) { .. run script between brackets if true ...}.  If the condition within the parentheses is true, the  script right after within the braces runs if the condition is true. Be careful, do NOT put a semi-colon after the parenthesis between the closing parenthesis )  and opening bracket {. | if&#160;(age&#160;>=&#160;18)<br />{<br />&#160;&#160;&#160;draw_text(x,&#160;y,&#160;"adult");<br />}                                                            |
| else if statement    | An "else if" statement comes after an if() or else if() statement  (they can be chained).  The next else if runs if the previous statement resolves  to false.Be careful, do NOT put a semi-colon after the parenthesis between the  closing parenthesis ) and opening bracket {.                                                                     | if&#160;(age&#160;>=&#160;18)<br />{<br />&#160;&#160;&#160;draw_text&#160;(x,&#160;y,&#160;"adult");<br />}<br />else&#160;if&#160;(age&#160;==&#160;17)<br />{<br />&#160;&#160;&#160;draw_text(x,&#160;y,&#160;"17&#160;year&#160;old");<br />} |
| else                 | After a chain of if and else if statements, if none of them are true you can  create a final statement that will always run with else.                                                                                                                                                                                                                | if&#160;(age&#160;>=&#160;18)<br />{<br />&#160;&#160;&#160;draw_text(x,&#160;y,&#160;"adult");<br />}<br />else<br />{<br />&#160;&#160;&#160;draw_text(x,&#160;y,&#160;"minor");<br />}                        |
| == expression        | If the value on either side of the == operator are identical then the result is  true.  If the values are not the same it returns false.                                                                                                                                                                                                              | if&#160;(i&#160;==&#160;j)<br />{<br />&#160;&#160;&#160;draw_text(x,&#160;y,&#160;"i&#160;and&#160;j&#160;are&#160;the&#160;same";<br />}                             |
| != expression        | If the value on either side of the != (not equal) operator are different then the result is true.  If the values are identical the return is false.                                                                                                                                                                                                   | if&#160;(i&#160;!=&#160;j)<br />{<br />draw_text(x,&#160;y,&#160;"i&#160;and&#160;j&#160;are&#160;different";<br />}                              |
| > expression         | Returns true if the value on the left is greater than the value on the right. Otherwise returns false.                                                                                                                                                                                                                                                | `if (age > 17)`                                                                                              
| >= expression        | Returns true if the value on the left is greater or equal to the value on the  right. Otherwise returns false. | `if (age >= 18)`                                                                                                            
| < expression         | Returns true if the value on the left is less than the value on the right. Otherwise returns false.                                                                                                                                                                                                                                                   | `if (age < 19)`                                                                                                           
| <= expression        | Returns true if the value on the left is less or equal than the value on the  right.Otherwise returns false.                                                                                                                                                                                                                                          | `if (age <= 18)`                                                                                                           
| function             | A function is a block of code that performs a function.  It then can return a value.  You may or may not need to pass the function arguments that it  needs to perform its task.  foo = function_name(argument0, argument1...); calls a function, sets the return value to foo and and passes arguments.                                              | `av = average(3,4,5);` note: this function returns the real number of 4 that is stored in the `av` variable. |
| repeat loop          | Allows you to perform a task multiple times.  `repeat (10)` { enter script here }  will run what is between the brackets 10 times.                                                                                                                                                                                                                    |  margin&#160;=&#160;32;<br />repeat(lives)<br />{<br />draw_sprite(obj_heart,&#160;0,&#160;x,&#160;y);<br />x&#160;+=&#160;margin<br />}                        |
| for loop             | Allows you to perform a task multiple time.   for (staring_point, end_point, increment or decrement)                                                                                                                                                                                                                                                  | for&#160;(int&#160;i=0;i&#160;<&#160;lives;&#160;++i)<br />{<br />&#160;&#160;&#160;draw_sprite(obj_heart,&#160;0,&#160;i&#160;*&#160;margin,&#160;y);<br />}                          |
| sprite origin        | This is the x, y position in local space of the sprite that it is drawn from in the room.  It is also the point that the sprite rotates around when rotating                                                                                                                                                                                          | `sprite_set_offset(spr_player, 32, 32)`;                                                                     |
| errors               |    There are three types or errors that we care about the most in GameMaker.a<br />1. Compile Errors.  This is when you can't compile the script and run the game.  An error message pops up.<br />2. Run Time Errors.  Play the game and an action causes the game to crash, and an error message pops up.<br />3. The last is a logic error where the script is not doing what the author intended.                                                                                                                                                                                                                                                                                                                                                    |                                                                                                            |


## GameMaker Resources
On the right hand side of the game editor you have a list of all resources that can be added to the game.

| Game Maker Resources | Description                                                                                                                          |
|----------------------|--------------------------------------------------------------------------------------------------------------------------------------|
| Rooms                | Each level in GameMaker is called a room.  When you create a new project a room called `room0` is provided.                          |
| Sprites              | This is raster based artwork (pixels) and can be created in GameMaker or any pixel based editing software like Photoshop.            |
| Objects              | The only object that can interact in the level is a GameMaker Game Object. Objects can bind sprites, run scripts and trigger events. |

## GameMaker Events
GameMaker can only run scripts on given events.  The below are the most common event types we use.

| Game Maker Events | Description                                                                                                                                                                                                                                                                                                                 |
|-------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Draw              | A Draw event allows you to alter what the object draws on top of, or instead of the sprite.  If you still want to draw the sprite in that event you need to include draw_self().                                                                                                                                            |
| Create            | A Create event is run once when the object is first instantiated in the room.  If it is in the room, it is run when the game is played or it is run when the object appears if it is dynamically generated by script.  It is often used to set the assign the default value to variables that will be used in other events. |
| Step              | A Step event is run every frame based on the frame rate of the game.  The default value is usually 30 frames per second.  We ONLY use this event for scripts that need to be continually updated.  So things like polling for controller input would be put in a Step event.                                                |

## Built in Object Variables
GameMaker objects all share common built in variables.  Here are the ones that are important to this exercise.

| Built-In Object Variables | Description                                                                                                                                                                                                                       | Example                  |
|---------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------|
| x                         | This is the location horizontally in the room along the x axis for the game object. A positive `x` value is to the right and negative `x` value to the left.                                                                      | x&#160;=&#160;200;                 |
| y                         | This is the location vertically in the room along the y axis for the game object. A positive `y` value is to the bottom and negative `y` value to the top. This is the opposite of how a y axis would be represented in geometry. | y&#160;=&#160;150;                 |
| image_angle               | The angle of rotation of the sprite. 360 degrees represents an entire rotation. 0 is to the right, 90 is pointing up, 180 is pointing in the other direction and 270 is pointing down.                                            | image_angle&#160;=&#160;90;        |
| vspeed                    | Vertical component of the speed of the player in pixels per frame.                                                                                                                                                                | vspeed&#160;=&#160;5;              |
| hspeed                    | Horizontal component of the speed of the player in pixels per frame.                                                                                                                                                              | hspeed&#160;=&#160;5;              |
| direction                 | This is an angle in degrees of the direction the vehicle is moving in (which could be different than the image_angle)                                                                                                             | direction&#160;=&#160;image_angle  |
| speed                     | This is the speed that the object is moving in pixels per frame along the direction axis.                                                                                                                                         | speed&#160;=&#160;7;               |
| room_height               | This is the width the room in pixels.                                                                                                                                                                                             | y&#160;=&#160;room_height&#160;/&#160;2;      |
| room_width                | This is the height of the room in pixels.                                                                                                                                                                                         | x&#160;=&#160;room_width&#160;/&#160;2;      |
