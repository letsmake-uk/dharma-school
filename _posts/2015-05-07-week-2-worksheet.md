---
layout: post
title: Week 2 - Worksheet
---

## Paper Switch

<br>
So far we have been using a breadboard and jumper wires to prototype our circuits. This is super useful when we are still playing with our circuit design, because it lets us rearrange things very quickly and easily. What about when we are happy with our design and want to keep it? Well, one way that we could do this is to use conductive tape, and lay our circuit out on paper. 


This is our switch circuit laid out with conductive tape. To close the switch all we need to do is to fold down the corner so that the 5V connection touches the connection going to pin 2. You can even add little female jumper wire attachments so that your switch is super easy to wire into your Arduino, like I have done here.

![Paper Switch](../img/paperSwitch.png "Paper Switch")


![Open Switch](../img/CIRCUIT switchOpen.png "Open Switch")

The paper circuit is exactly the same as our switch from last week. If you look closely all the same things connect together. As long as electricity flows around our circuit in the same way, it will behave exactly the same. If we pop an LED in pin 13, we can use this same block of code from last week to turn the LED on and off.


![Digital Switch](../img/LED digitalSwitch.png "Digital Switch")



## Morse Code

<br>
Some of you last week noticed that with our LED switch, we could send messages in <a href="http://en.wikipedia.org/wiki/Morse_code">Morse code</a> if we wanted to. This is a really cool idea, so we thought we'd look at it in a bit more detail and see if we can maybe even get scratch to send some messages in morse code by itself. For those of you that don't know what Morse code is, here's the wikipedia definition : 

> Morse code is a method of transmitting text information as a series of on-off tones, lights, or clicks that can be directly understood by a skilled listener or observer without special equipment.

It was developed in the 1830's to send messages quickly over long distances using an <a href="http://en.wikipedia.org/wiki/Electrical_telegraph">electrical telegraph.</a> It was invented a several decades before the telephone, and was so useful it was still used at sea until 1999. 


Here is a chart of the letters A-Z, and the numbers 0-9 in Morse Code :

![Morse Alphabet](../img/International_Morse_Code.png "Morse Alphabet")

The timing between the dots and dashes is important because we don't want our message to be misunderstood. Everything depends on how long a single dot is, so if a dot was 1 second long : 

- A dash would have to be 3 seconds long.
- The space between two parts of the same letter would have to be 1 second long.
- The space between letters would have to be 3 seconds long.
- The space between words would have to be 7 seconds long.

<br>
Using a whole second for a dot would take aaaaages to send a very long message so we probably don't want to do that. Have a look at these words, and see if you can translate them. Notice how many seconds each one would take if each square was a second : 

<br>
![Morse 1](../img/Morse_Mo.png "Morse 1")
<br>
![Morse 2](../img/Morse_Nic.png "Morse 2")
<br>
![Morse 3](../img/Morse_Louis.png "Morse 3")

## Morse code challenge

<br>
Let's try and write our own program to send Morse code. We have made this little guy out of a light dependent resistor (something we will look at next week) and programmed him so he can read your morse code transmissions!

So that we can understand everyone's Morse code, let's all use 0.1 seconds as the length of a dot. This means that :

- A dash would have to be 0.3 seconds long.
- The space between two parts of the same letter would have to be 0.1 second long.
- The space between letters would have to be 0.3 seconds long.
- The space between words would have to be 0.7 seconds long.

<br>
Have a go at making a program that sends your name in Morse code, and then we'll talk about how different people have approached the problem, and show you how we decided to do it.



## Paper Circuits

We could use lots of other things instead of wires to create our circuit. Anything that conducts electricity will work. Conductive tape is really handy, but if you don't have any at home you can try using things like paperclips and tin foil. You can even buy special <a href="http://www.bareconductive.com/shop/
">paint</a> now that conducts electricity, and even <a href="https://123d.circuits.io/shop/circuitscribe#accessories">pens</a> that write with conductive ink. 


Here are a few cool projects for inspiration.


<iframe width="640" height="480" src="https://www.youtube.com/embed/AI-6wMlaVTc" frameborder="0" allowfullscreen></iframe>

 

<iframe src="https://player.vimeo.com/video/40904471" width="640" height="360" frameborder="0" webkitallowfullscreen mozallowfullscreen allowfullscreen></iframe> <p><a href="https://vimeo.com/40904471">Interactive Light Painting: Pu Gong Ying Tu (Dandelion Painting)</a> by <a href="https://vimeo.com/user1892233">Jie Qi</a><p>

http://www.creativeapplications.net/sound/paper-electronics-by-coralie-gourguechon/


Arduino free paper circuit ideas:


http://highlowtech.org/?p=2505


 - Talk about soldering / proto boards
 - Talk about PCB etching
 - Hook up the switch to turn pin 13 on/off



