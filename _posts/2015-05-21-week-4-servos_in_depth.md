---
layout: post
title: Week 4 - Servos in depth
---

Last week, we gave you an introduction to the wonderful world of servos. Our versatile little friends are used in hundreds of different ways, from robot arms, legs and steering to the regulators and switches keeping power plants from blowing up!

Here's a reminder of the important details:

This is the diagram showing you how to wire up your servo. Remember the wires on your ones may be slightly different colours, but they all work the same.  

 - Red           : 5V
 - Black/Brown   : Ground
 - Yellow/Orange : Pin 8 (control signal)

<br>
<br>
![Servo diagram](../img/servo_circuitDiag.png "Servo diagram")

We used some of the jumper wires we gave you in the first class to bridge the connection between the sockets on the servos and our breadboard - the colours of the jumper wires are not important, but you might find it easier to use the same colours as the wires coming out of the servo!

We showed you that you can find the control block for a servo in the usual "motion" section of S4A: it's the one that says "motor **8** angle **180**". This block sets the **angle** of the servo arm connected to pin **8** to anywhere between 0 and 180 (just like the angles on a protractor!).

<br>
![protractor](../img/protractor.png "protractor")


<br>
Most of you will have put together an example control loop that looked something like this, which tells your arm to wiggle back and forth from 0 to 180 every second:


![servo wiggle](../img/servo_wiggle.PNG "servo wiggle")


<br>
And some others might have used broadcasts to control the wiggling with keypresses:


![Servo 1](../img/servo1.png "Servo 1")


<br>
But today, rather than just moving from one side to the other like a wind-screen wiper (or a waving machine!), we'd like to show you how to use key-presses to move the servo arm bit-by-bit, to any position between 0 and 180. And to make our lives easier we're going to be using all of the tricks we learned in our morse-code examples from weeks 2 and 3.


## Variables

<br>
If we want to move our servo only a little bit left or right, we need to have a way of knowing where it is. We can do that by storing our servo angle in a **variable**. Variables are a really important concept in programming. We use them whenever we need a number we can use in lots of different places in our code. Using variables instead of "hard coded" numbers means that if we change the value of our variable, all of the places in our code where we use it will automatically use the new value. To make a new variable in Scratch, go to the variables section and click on "Make a variable"


![Make a variable](../img/var_createVar.PNG "Make a variable")


<br>
A window will pop up asking what you want to call your new variable. We want a number to store the current angle of our servo motor, so we are going to call it "servoAngle" It is always a good idea to name your variables with a good description of what they are used for. It helps you remember what it's for, and it makes your code easier to understand.

![servo angle variable](../img/var_createServoAngle.PNG "servo angle variable")


<br>
Once you have created a variable, some new blocks will pop up in the variables section. These are what we will use whenever we want to modify our variable, or use it in our program. The most important ones are the "set servoAngle to..." block, and the round "servoAngle" block.

![Variable blocks](../img/var_varBlocks.PNG "Variable blocks")


<br>
Below is our program changed so that it uses the new variable. We first set our variable to what we want it to be, then instead of typing in numbers to the "motor 8 angle" block we use the round "servoAngle" block.

![Servo 3](../img/servo3.png "Servo 3")


<br>
Now what we can do is add or subtract stuff from this variable, and our servo will move left or right just a little bit from wherever it already is. There is a bit of a problem with this code though, have a play around and see if it behaves in a way you didn't expect.

![Servo 4](../img/servo4.PNG "Servo 4")


<br>
You might have noticed that when we move below 0 or above 180, the servo doesn't go back the other way straight away. This is because our variable is going outside the 0-180 range of our servo, and when we start moving back the other way, we have to wait for it to come back inside the range. This is probably not how we would like it to behave.

<br>
![Servo 5](../img/servo5.PNG "Servo 5")


<br>
To fix this what we need to is, when we move left check whether servoAngle has gone below 0. If it has gone below 0 we want to set it to 0. Also, every time we move right, check whether it has gone above 180 and if it has, set it to be 180. This way our variable will never go outside the range 0-180.
 

To do this, we will have to use some of the green "operators" blocks. 

  - The " < " block checks whether what's on the left is *smaller* than what's on the right
  - The " > " block checks whether what's on the left is *bigger* than what's on the right


<br>
<br>
![Servo 6](../img/servo6.PNG "Servo 6")


<br>
This is much better, and probably works the way you would expect it to. Now what if we wanted to make it go faster or slower? Again, we don't want to have to change this in two different places so let's make a new variable called "servoSpeed", set it to something bigger than 5, then use this value in our servoLeft and servoRight code.

![Servo 7](../img/servo7.PNG "Servo 7")

Now if we want to make our servo move at a different speed all we have to do is change our "servoSpeed" variable. We could even add keyboard shortcuts to change the speed if we want to, and use the same techniques to limit the range of values. See if you can work out how to do this...