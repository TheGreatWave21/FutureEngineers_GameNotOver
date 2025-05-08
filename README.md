GameNotOver
====

This repository contains engineering materials of a self-driven vehicle's model participating in the WRO Future Engineers competition in the season 2025.

## Directories

* `t-photos` contains 2 photos of the team (an official one and one funny photo with all team members)
* `v-photos` contains 6 photos of the vehicle (from every side, from top and bottom)
* `video` contains the video.md file with the link to a video where driving demonstration exists
* `schemes` contains one or several schematic diagrams in form of JPEG, PNG or PDF of the electromechanical components illustrating all the elements (electronic components and motors) used in the vehicle and how they connect to each other.
* `src` contains code of control software for all components which were programmed to participate in the competition
* `models` is for the files for models used by 3D printers, laser cutting machines and CNC machines to produce the vehicle elements. If there is nothing to add to this location, the directory can be removed.
* `other` is for other files which can be used to understand how to prepare the vehicle for the competition. It may include documentation how to connect to a SBC/SBM and upload files there, datasets, hardware specifications, communication protocols descriptions etc. If there is nothing to add to this location, the directory can be removed.

## Contents

* [**The car**](#Design)
    * [**Components**](#Components)
    * [**Chassis**](#Chassis)
    * [**The 3D-printed Parts**](#3D-printed-parts)
* [**Documentation**](#documentation)
* [**Photos and Videos**](#p--v)
    * [**Programming language**](#programming)
    * [**The Coding**](#code)
    * [**Explanation**](#explanation)
* [**Self-reflection**](#betteringself)




# The car

Our robot consists of two main parts. The electronics and the chassis. The electronics include the brain of the car, which is the Arduino Potenta and the Arducam, which it could not work without. The Eletrical motors are also part of the electronic system, as well as the steering of the car. Battery is also included. The chassis part of the car includes the Wheels and the mechanic way of turning the wheels.    --to be continued

## Components

This list contains all the materials that were used to build our Robot. This includes everything (except 3D-printed parts, which are not included here. More about them later):
1. Computer: Arduino Mega
2. Batterie: Gens ace Modellbau-Akkupack (LiPo) 11.1 V 1200 mAh Zellen-Zahl: 3 25 C Block
3. Motor: Motraxx SR540SH-6230S-67 Universal Brushed Elektromotor
4. Motortreiber: Cytron MD10C
5. Mini Cam: Arducam 5MP Plus OV 5642 Mini Cam
6. Ultraschallsensor: HC-OSR4
7. Farbsensor: APDS-9960 


## The 3D-printed parts 

We 3D-printed the chassis of the car to be able to contain the color sensor, the Arduino Mega, the motor drive and the distance sensors. They have been accomodated accordingly on the chassis. This can be seen on the following pictures:

# Documentation

As a team, we first thought of how to structure the car in a way, that is easy to then drive with. The length x width x height of the car couldn´t exceed more than 30 x 20 x 30 cm, so we had to get creative. In the end, we decided to go for a square design, since this was the most efficient easy to store every component. 3D printing almost every structural part, was a important idea, since the car should not exceed a maximum of 1,5 kg in weight. The car also should not drive on less than 4 normal wheels, which means for us that our initial design is not adequate anymore. We started to print but soon noticed that the design of the car was not fitting at first, so we changed to the design that we know would work. 

# Photos and Videos

![Base of the car in the 3D printer](https://github.com/user-attachments/files/19326566/IMG_5110.pdf)

![3D printed](https://github.com/user-attachments/files/19326567/IMG_5111.pdf)

![3D printed](https://github.com/user-attachments/files/19326568/IMG_5112.pdf)

You can see the base in the 3D printer.

![The base without the supporting bars](https://github.com/user-attachments/files/19326545/IMG_5109.pdf)

You can see the unfinished base without the "sticks", which are going to give stability to the whole vehicle and hold our control system. (arduino potenta)

![Design software](https://github.com/user-attachments/files/19326527/IMG_5108.pdf)

Here you can see the robot in the 3D printing design software. This part will only be used for the base.

# Programming language

In the end, we decided to use Python as our main programming language on an Arduino Mega. The code is explained under the explanation part of this repo. 

# The Coding

#define PWM_PIN 9  // Connects to PWM on MD10C
#define DIR_PIN 8  // Connects to DIR on MD10C

void setup() {
  pinMode(PWM_PIN, OUTPUT);
  pinMode(DIR_PIN, OUTPUT);
}

void loop() {
  digitalWrite(DIR_PIN, HIGH); // Set direction
  analogWrite(PWM_PIN, 200);   // Adjust speed (0-255)
  delay(2000);

  digitalWrite(DIR_PIN, LOW);  // Reverse direction
  analogWrite(PWM_PIN, 200);
  delay(2000);
}
// Motor dreht in eine Richtung (vorwärts)
  digitalWrite(DIR_PIN, HIGH);  // Setze die Richtung auf HIGH
  analogWrite(PWM_PIN, 200);    // Setze die Geschwindigkeit auf 200 (0-255)
  delay(2000);                  // Warte 2 Sekunden

  // Motor dreht in die entgegengesetzte Richtung (rückwärts)
  digitalWrite(DIR_PIN, LOW);   // Setze die Richtung auf LOW
  analogWrite(PWM_PIN, 200);    // Setze die Geschwindigkeit auf 200
  delay(2000);                  // Warte 2 Sekunden
}

# Explanation

--to be continued

# Self-reflection

--to be continued

