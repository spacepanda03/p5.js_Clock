# p5.js_Clock
Creative Coding Assignment of FTA134

https://editor.p5js.org/spacepanda0304/sketches/N-IU3hIfF

Through learning the P5.js framework, I discovered that I can manipulate the visual elements on the screen by detecting the state and position of the mouse. For instance, I can change an element's fill, size, or position by clicking, dragging, or pressing the mouse over it. Therefore, I came up with an idea. To create a desktop pet in Visual Clock that can interact with the user easily, which can move to and fro within a defined range, changing its direction when it reaches a wall, while the user can control its grabbing and moving with the mouse. 
To accomplish this idea, I first created an animation of a character walking and exported it as a sequence of images saved in the p5.js folder, then used a for loop statement to iterate over the folder and import the images. Next, I defined a class and implemented the character’s animation playback logic in it, so that it was convenient to invoke the class directly when using it later. 
The first challenge I faced was that when I finished the repeated movement of the character in the specified area, I realized that my character could not change the direction of the image after touching the wall. To address this, I attempted to use a walking animation that adds another direction but failed. So, I tried to resolve this issue by changing the “scale (x, y)” X value to a negative number. The issue was that when X was changed to a negative number, the position of the image also shifted to the opposite direction. So, I modified position [0] to negative again. 
After finishing the previous section, I attempted to add a behavior for the desktop pet to interact with the user, so I added a new image, but I realized that this image changes direction along with the character, while the image as the background does not. After checking my code and looking up information, I concluded. “Scale (x, y)” controls the parameters of the whole, but the background does not change so it remains as it is. To solve this problem, I wrapped “scale ()” with “push ()” and “pop ()” so that he only controlled the character's walking transformation, and then set the position of the new image to “( mouseX, and mouseY )”. At this moment, when the mouse grabs the character, the character’s walking animation and the grabbed image will be displayed concurrently. Since I did not put the two sets of images into the array earlier, I added a command to the character’s class to change the transparency of the walking animation to 0 when the mouse is pressed.
After accomplishing the code for the desktop pet character part, I moved on to work on the most important clock part. So, I intended to represent the flow of time through the cycle of day and night and the switch of the room lights after dark. At the same time, at 6 a.m., the night gradually brightens and the sun rises. At five o'clock in the afternoon, it is sunset. I use the “hour ()” and “minute ()” functions to read the computer’s time. Then, I use an if statement to add different content for different time periods. I found that the statement “let hour = hour ()” must be written within the draw function; otherwise, the program will not run. Instead of creating a new class for the background transformation, I wrote all the code within the draw function. The transparency modification is controlled by the “push ()” and “pop ()” functions, which cycle between two images representing day and night to achieve the alternation of day and night. However, the “rotation” of the sun and moon created a new problem. Due to the rotate command causing the image to rotate around the center point (0,0), even though the center of the image was set to the middle of the image, it still rotated around the rotation center. I tried to use translate to change the center of rotation, but this approach was abandoned due to issues with the image. The final solution was to use “translate” to create an effect like the rising of the sun and moon. Finally, I wanted to make my character livelier, so I added sound to my character.
