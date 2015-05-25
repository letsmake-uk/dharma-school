---
layout: handout
title: Voltage divider
---

<br>

A lot of the input circuits we're working with today work on the principle of a 'voltage divider' (e.g. the Light Dependent Resistors, the potentiometers, and even the push-button switches).

A voltage divider is a simple circuit which turns a high voltage (*V<sub>in</sub>*) into a lower one (*V<sub>out</sub>*). The circuit can be drawn in many ways, but below is a pretty typical way of showing it (<a href='https://commons.wikimedia.org'>cc Wikipedia</a>)


![Voltage divider](../img/voltage-divider.svg "Voltage divider")


We call the resistor closest to *V<sub>in</sub>* R1, and the resistor closest to ground R2. The voltage drop across R2 is called *V<sub>out</sub>*, and that's the voltage we measure or use to drive other circuits. 


We can calculate what *V<sub>out</sub>* would be if we know *V<sub>in</sub>* and the resistances by using the voltage divider equation:


![Voltage divider equation](../img/voltage-divider-equation.png "Voltage divider equation")


Do you see R1 there in the denominator? That means that if we *increase* R1, we *decrease* *V<sub>out</sub>* and vice-versa. Likewise if we *increase* or *decrease* R2, we *increase* or *decrease* *V<sub>out</sub>* in turn!