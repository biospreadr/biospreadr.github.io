---
title: "Mechanical Experiments and Carrier Tube Progress"
date: 2021-03-01
image: "images/481_scotch_yokes.png"
# author
author: ["Biospreadr Team"]
# categories
categories: ["Weekly updates"]
tags: ["update"]
# meta description
description: "Mechanical Experiments and Carrier Tube Progress"
# save as draft
draft: false
---

# Week 7

This week we were able to make great progress on both the Carrier Tube mechanism and on our Mechanical Simulation work.

## Mechanical Simulation: Experimenting

### COVID-19 Considerations
Due to the limitations caused by the COVID-19 pandemic our team has had to make significant modifications to our designs which were made with the intent of developing **BioSpreadr** in an in-person, lab context. This has been the biggest challenge we have faced throughout the term as we have had to make alterations to all components of our project. The elements most impacted by the COVID limitations were the mechanical ones. Due to our team being located in distanced locations, we won't be able to assemble all of our sub mechanisms into the integrated system that we initially designed. Additionally, due to restrictions on resources we were unable to make certain elements of each sub mechanism, including the scotch yolk mechanism. As mentioned in our previous blog post, our team decided to fully simulate this component of **BioSpreadr**. Doing so allowed us to make meaningful use of our time and make detailed developments on the Mechanical design instead of spending much of our time navigating development of a physical prototype during a pandemic.

### Shaking Experiment
Ideally tests with a completed version of **BioSpreadr** could be performed to ensure that the shaking of the Petri dish would be sufficient. With a full machine, there would be control over the direction of motion and the speed. Without the full machine it is almost impossible to control both of these aspects. To try and make the experiment as consistent as possible, a linear guide was purchased which would keep the direction and distance of motion consistent. A metronome was used as a guide for the speed of the back and forth motion. Food coloring was used to make it easier to see where the sample solution would be spread.
The following videos demonstrate the experiment with the Petri dish moving 100 mm at 100 rpm as specified in the design. Halfway through the shaking, the Petri dish was turned 90 degrees to mimic the machine having two axes of motion.

![Experiment (1)](https://media.giphy.com/media/UeNIiZadkAYgkdjsJP/giphy.gif)

![Experiment (2)](https://media.giphy.com/media/vWKF6BwjYOhvlj26JX/giphy.gif)

The following photo was taken after the experiment shown in the previous videos. It shows very good coverage of the Petri dish which indicates that a fully assembled prototype, using the designed shaking method, would be sufficient to ensure a suitable spread of the sample.

![Sensor graph](/images/wk7_finished_experiment.JPG)

Overall, this is exciting progress for our mechanical simulation work and gives us further confidence that if we were to build a full prototype of **BioSpreadr**, it would be effective in achieving its purpose (see our [About](https://biospreadr.github.io/about/) page to read more on our purpose).

## Carrier Tube: Software Updates

This week we were able to get the electrical/software elements of the Carrier Tube mechanism in a final state. We may still make modifications, but we aren't currently facing any blockers on develompent progress.

### Power System
As discussed in previous blog posts, figuring out the best way to power our system was a significant challenge. The final system we are using consists of two repurposed chargers as power supplies:

- A 12VDC, 300mA supply plugged into the power jack of the Arduino
- A 7.5VDC, 2A supply stripped and plugged into the motor terminals of the shield

The solenoid is rated for 6V but we were unable to power it with previous 5V and 6V supplies that we were using, mainly due to loss through the motor shield. Since we are controlling our solenoid using PWM signal, the 7.5V supply gave us a lot of flexibility. We had more than enough supply voltage so we could change the duty cycle of the PWM signal being sent to the solenoid such that it received the required 6V.

### Button Input
After finalizing the power system, we needed to introduce user control to the mechanism. At first we considered using an external push button through a breadboard. To make a more compact mechanical design, for now we have opted to repurpose the reset button on the Arduino to control the mechanism. This was done by utilizing the capability to set variables that are not initialized on reset/startup (`.noinit`). Using this, we developed code that handles 3 different modes during the operation of the mechanism:
1. Waiting state (once powered on, the LED on the Arduino flashes to indicate waiting until the button is pressed)
2. Fill the Carrier Tube with beads (after the button is pressed, the solenoid is engaged allowing it to fill with beads)
3. Dispense beads (once the tube is filled, disengage the solenoid to allow beads to fall into the Petri dish)
    * This step will happen after a set wait time (long enough to fill the beads) or if the button is pressed again

Next, we will be focusing on development of a mechanical housing for the Carrier Tube mechanism. Until we have that we can't properly test out the filling/dispensing of beads with the Carrier Tube. The following video demonstrates the mechanism working without the housing.

![Carrier Tube Working](https://media.giphy.com/media/Vihc3akPXWyrFzTAx6/giphy.gif)
