# Biosignal Kinematics Mapping


## Introduction
   This project is the R&D process of a tool that is attached to the user's hand, arm, and scalp in a minimally invasive way. This started as an idea for simply a glove and evolved (or devolved, depending on who you ask) into a full blown sleve. The outputs from this smorgasbord of sensors get dumped into a program to interpret them in what I hope to be real time (<250ms). There are a few forms this data analysis could be structured into such as a live 3d model, or CSV of quaternions (a number system I will talk about later). This project could be useful in a number of situations, from robotics control, to computer inputs, or as a gesture-to-speech system.

## Hand
   Starting with the part of this project that is both the easiest to make with limited resources, as well as being the fundamental part of this, the glove sensors.

### Initial Hand Design
![Image failed to load](handSketch.jpg)

The most common causes of output drift in an IMU chipset are to the gyroscope, and are caused by heat and angular random walk (ARW) caused by high frequency noice. The first one can simply be solved by placing a small fan and/or heatsink, or alternatively heat shielding around the arduino. ARW can be negated by the fusion of sensors, so if gyroscope changes without change in magnetometer (or vice versa) the input may be voided. This does cause issues, such as if a magnet throws off the magnetometer then the hand is rendered useless. The flex sensors may shift from their initial mapping slowly over time, but this can be fixed with a simple calibration. Methods to test the accuracy may be installed, but recalibration is both more simple, and a better habit to have in place. Every sensor is susceptible to drift, but pairing sensors to create redundancies also allows for correction of any issue of this extent. Another benefit of having a greater number of contrasting sensors is it allows detection of a larger variety of things that can be implemented into the calculations.
