---
title: "More progress on the Carrier Tube Mechanism"
date: 2021-02-07
image : "images/481_scotch_yokes.png"
# author
author : ["Biospreadr Team"]
# categories
categories: ["Weekly updates"]
tags: ["update"]
# meta description
description: "More progress on the Carrier Tube Mechanism"
# save as draft
draft: false
---

# Week 4

## Carrier Tube: Mechanical Updates
After getting the initial prints completed last week, this week was spent refining the mechanics of the carrier tube system and testing everything prior to handoff for electrical/software integration. Initial test fits revealed that the solenoid cavity in the 3D printed part was too small to fit the solenoid. There was a similar problem last week with the inner carrier tube being too small which was solved by sanding down the part. Unfortunately, sanding down the solenoid was not an option.
 
Consequently, the main body of the carrier tube was re-printed at 103% scale, which ensured that there was enough clearance for all components without the need for post-print finishing. Once the reprint was complete, the whole mechanical system was put together and tested by hand. The completed system is shown below:
 
![Carrier Tube Mockup](/images/wk2-carrier-tube-mockup.jpg)
 
The photo shows the main body with the solenoid and piston inside, as well as the inlet and outlet bead feeding tubes installed. Manual operation showed that the system consistently dispenses the correct number of beads without jams or other malfunctions. This represents the achievement of a key design goal for the Biospreadr apparatus.
Next steps for the carrier tube include mechanizing the system by powering the solenoid and adding software control.

## Carrier Tube: Testing the power system

Once the mechanical components for the carrier tube assembly were in good shape, the electrical integration was started. We are using an Arduino Uno Rev3 board which runs on 7-12V DC and can supply up to 5V DC and 50mA. This current is not sufficient to run the solenoid we're using to move the carrier tube which requires 800mA when running at 5V DC. To solve this issue, we are using a motor shield that can output up to 1.2A. The motor shield is also needed to protect the rest of the circuit from the inductive kickback generated when powering off the solenoid.

Due to these different specifications, two power supplies are needed - one for the Uno and one for the motor shield. The Uno requires max 200mA so we decided to use a household brick power supply that can provide 12V DC and 300mA. Initially, we tried to us a 4-pack of batteries in series to power the motor shield and solenoid. After some testing we found that the batteries could only supply less then 600mA at 6.5V DC, which is not sufficient to meet the solenoid requirements. As a second alternative, we are trying out a repurposed iPhone charging block supplying 5V DC and 1A. The following image shows the stripped charging cable that will be used as a supply. To prevent the supply from shorting, a significant amount of the cable was stripped and the positive and negative wires bent away from each ohter. 

![DIY iPhone charger](/images/wk2-diy-supply.jpg)
![DIY iPhone charger (1)](/images/wk2-diy-supply-2.jpg)

The next step is to test out whether the iPhone charger will successfully power the solenoid. Assuming all goes well, we will then be ready to put together the entire electrical assembly and start writing and testing out the software.
