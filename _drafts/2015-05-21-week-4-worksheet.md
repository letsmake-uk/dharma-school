---
layout: post
title: Week 3 - Servos
---

So now we will look at how we can use all the lessons we have learned from doing our morse code to help us make something a bit more robot-y, and control a servo motor. Servo motors are used all over the place in robotics. Servo motors are different to regular motors, because we can tell them exactly where to move to, which is pretty handy when you want your robot to move it's arm to a specific place.


So far, we have only had to plug our components into 2 pins on the Arduino, one into 5V power, and one into ground. This is like plugging it into the two ends of a battery. Our servo needs power just like anything else, but if you look at the servo you'll see it actually has 3 wires. This is because we also need to be able to send it a control signal to tell it where to go.


Here is a diagram showing you how to wire up your servo. The wires on your ones are different colours to this diagram, but they do the same thing. 

 - Red           : 5V
 - Black/Brown   : Ground
 - Yellow/Orange : Pin 8 (control signal)

<br>
<br>
![Servo diagram](../img/servo_circuitDiag.png "Servo diagram")

If you look in the "motion" section, where all of our arduino blocks are, you should see one that says "motor 8 angle 180" This is the block that sends a control signal to the servo to tell it where to rotate to. The reason it says 180 is because that is the maximum range of our servos. This means it can move around anywhere within a half circle.


Try sending it a value of 180, then sending it a value bigger than 180. It doesn't move because it is already as far right as it can go. The same thing will happen if you send it a 0 and then send it a number smaller than 0 (eg -10)

<br>
![protractor](../img/protractor.png "protractor")


<br>
Here is a simple program that makes our servo wiggle back and forth.

![servo wiggle](../img/servo_wiggle.PNG "servo wiggle")

<br>
But what if we want to be able to control our servo manually? Let's use the things we learned sending morse code and see if we can make a cool control system using the keyboard. First of all, we want to create broadcast messages for servoLeft and servoRight. Then we will call these every time we press the left and right arrow keys. 

Now we can wiggle our servos around manually, woooohooo!

![Servo 1](../img/servo1.png "Servo 1")


<br>
Here we have combined these two programs so we have a wiggling servo that also has keyboard control. You might be wondering why we have used broadcasts for such a simple program. What we actually want our program to do is move the servo only a little bit left or right, and we are going to add stuff to our servoLeft and servoRight code so that we can do this.

![Servo 2](../img/servo2.png "Servo 2")


<br>
If we want to move our servo only a little bit left or right, we need to have a way of knowing where it is. We can do that by storing our servo angle in a variable. Here we have made a new variable called servoAngle, and changed our code to use this instead of typing in numbers to the "motor 8 angle" block.

![Servo 3](../img/servo3.png "Servo 3")


<br>
Now what we can do is add or subtract stuff from this variable, and our servo will move left or right just a little bit from wherever it already is. There is a bit of a problem with this code though, have a play around and see if it behaves in a way you didn't expect.

![Servo 4](../img/servo4.PNG "Servo 4")


<br>
You might have noticed that when we move below 0 or above 180, the servo doesn't go back the other way straight away. This is because our variable is going outside the 0-180 range of our servo, and when we start moving back the other way, we have to wait for it to come back inside the range. This is probably not how we would like it to behave.

<br>
![Servo 5](../img/servo5.PNG "Servo 5")


<br>
To fix this what we need to is, wheen we move left check whether servoAngle has gone below 0. Also, every time we move right, check whether it has gone above 180.


To do this, we will have to use some of the green "operators" blocks. 

  - The " < " block checks whether the thing on the left is *smaller* than the thing on the right
  - The " > " block checks whether the thing on the left is *bigger* than the thing on the right


<br>
![Servo 6](../img/servo6.PNG "Servo 6")


<br>
This is much better, and probably works the way you would expect it to. Now what if we wanted to make it go faster or slower? Again, we don't want to have to change this in two different places so let's make a new variable called servoSpeed, set it to something bigger than 5, then use this value in our servoLeft and servoRight code.

![Servo 7](../img/servo7.PNG "Servo 7")