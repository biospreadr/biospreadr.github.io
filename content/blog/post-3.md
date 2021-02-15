---
title: "Starting on the Suction Mechanism and Carrier Tube progress"
date: 2021-02-14
image : "images/481_suction_mechanism.png"
# author
author : ["Biospreadr Team"]
# categories
categories: ["Weekly updates"]
tags: ["update"]
# meta description
description: "Starting on the Suction Mechanism and Carrier Tube progress"
# save as draft
draft: false
---

# Week 5

## Suction Mechanism: Mechanical Updates

After receiving parts for the suction mechanism, mechanical assembly came first. The main components of our suction mechanism are an ultrasonic sensor, suction cup, vacuum pump, and tubing which is used to lift and replace the lid on the Petri dish. The suction cup and ultrasonic sensor need to be held in fixed positions by a plate so that detection, lifting, and replacing of the Petri dish lid can be accomplished effectively. The plate we're using was machined out of a larger piece of acrylic, which was the best option available despite being a little thick. The sensor bolts turned out to be shorter than expected so adding a countersink allowed each of them to be secured with nuts. Ideally, the bolts in the final product would be a bit longer to avoid this.
 
The plate thickness of about 0.5cm seems to be more than enough to support the components mounted to it, despite the decently heavy suction cup. The suction cup needed to be placed sufficiently off to the side so that it did not interfere with the sensor readings. The matching fitting was used as a reference for the hand tap size needed for the plate.

The plate with the sensor and suction cup attached can be seen below:
 
![Suction plate (1)](/images/wk1-plate-1.jpg)

![Suction plate (2)](/images/wk1-plate-2.jpg)

![Suction plate (3)](/images/wk1-plate-3.jpg)

## Carrier Tube: Electrical Updates

This week was a lot of troubleshooting for the work on the carrier tube mechanism. The datasheet for the solenoid indicated that it could operate when supplied 5-6V with 0.8-1A. After testing out various power supplies rated at 5V and 1-1.2A, the carrier tube was still not working as intended. As seen in the following video, the solenoid could only retract when assisted by an external force.

![Carrier tube assisted](https://media.giphy.com/media/BcucgcR1r321H8FTqu/giphy.gif)

We considered various causes for the issues we were experiencing including insufficient power capabilities of the supplies, faulty supplies, or faulty cables used to connect the supply to the motor shield. After further research, we were able to find more technical details about the solenoid which revealed that the solenoid would have weak performance if not supplied at least 6V. We were able to test the system using a variable power supply and confirmed that the solenoid needed 6V to operate properly when connected directly to the supply. After connecting the solenoid through the shield to the supply, it was still operating poorly (as it was when being fed 5V) despite being supplied 6V. It was determined that using the shield resulted in a significant voltage drop. All of the system components are rated to handle voltages above 6V and so we felt comfortable testing with a voltage of 7V being applied to the shield. Doing so resulted in the solenoid receiving around 6.5V which was enough to make it function properly, as seen in the following video.

![Carrier tube working](https://media.giphy.com/media/gThNMABSskNBb6IXn0/giphy.gif)

Now that we have the carrier tube working as expected, our next step will be looking for a fixed power supply that can provide sufficient power to the solenoid. We will also be working on the code required for the final design, which is similar to what we wrote to test the carried mechanism throughout this process. Finally, we will be working on the mechanical assembly needed to mount the carrier tube such that it can be used to dispense beads into the Petri dish.
