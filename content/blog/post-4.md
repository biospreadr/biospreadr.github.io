---
title: "Suction Mechanism Updates and Progress on Mechanical Simulation"
date: 2021-02-21
image: "images/481_scotch_yokes.png"
# author
author: ["Biospreadr Team"]
# categories
categories: ["Weekly updates"]
tags: ["update"]
# meta description
description: "Suction Mechanism Updates and Progress on Mechanical Simulation"
# save as draft
draft: false
---

# Week 6

## Suction Mechanism: Updates

### Construction

This past week was the Winter reading week, so we took advantage of the opportunity to make a lot of progress on the suction mechanism.

We were able to get the base construction complete including wiring for the controller, shield, vacuum pump, ultrasonic sensor, and power system. In addition to the base assembly, we integrated a push button to start the process of lifting the dish lid with the suction mechanism and an LED used for error signalling. Both of these peripherals required appropriately specced pull-down resistors.

The following two images show the updated system construction:

![Suction overview](/images/wk3-suction-overview.jpg)

![Suction wiring](/images/wk3-suction-wiring.jpg)

### Testing

After the initial construction of the system was complete, the next step was performing the relevant system tests.

The ultrasonic sensor being used to detect the success of lifting and dropping the lid on the Petri dish had to be characterized before the system could operate as intended.

![Suction cup and dish](/images/wk3-suction-cupanddish.jpg)

The conclusions from this characterization were that the sensor behaves linearly and has suitable accuracy over a reasonable use range, as described by the following graph:

![Sensor graph](/images/482-sensor-graph.jpg)
(Note: the sensor is not rated for distances less than 2cm)

Once the ultrasonic sensor was tested, the suction mechanism could be physically tested. The following video demonstrates the current operation of the suction mechanism. As you can see, the pump responds to the push button input, allowing the lid to be removed from the dish, and turns off after an appropriate wait time.

![Suction operation](https://media.giphy.com/media/2LLg5FPz1tQl7gIna5/giphy.gif)

### Software

As seen in the previous video, the general system process is as follows:

- Lower the suction cup to the lid of the dish
- Turn the vacuum pump on
- Raise the suction cup which is now suctioned to the lid
- Wait (for beads to be dispensed into the dish)
- Lower the suction cup with the lid
- Turn off the vacuum pump to release the lid
- Raise the suction cup to its initial position

Code was first written to setup the relevant I/O pins and to poll the push button input. The general system process could then be implemented in software. Finally, error handling was implemented to detect improper alignment of the dish lid and the suction mechanism, failure of the suction mechanism during the process, and failure of the mechanism to initially attach to the lid.

The error handling described is demonstrated in the following videos:

**Alignment and initial attachment error**
![Suction error](https://media.giphy.com/media/ymYyspDihJIDFyxg82/giphy.gif)

**Forcing the lid off mid-process**
![Suction error forced](https://media.giphy.com/media/6hRtBTwRIiMeW9G2dC/giphy.gif)

Overall, this was an exciting week for progress on the suction mechanism. Next steps will be modifying and improving the system layout and characterizing the suction mechanism to ensure optimal performance.

## Mechanical Simulation: Initial Updates

This week we were also able to make significant progress on our mechanical simulation. Due to COVID-19 complications our team opted for a highly detailed mechanical simulation instead of physically making either the scotch yoke mechanism, or the entire compiled BioSpreadr machine. Both of these weren't feasbile given our resources and restrictions this term.

We started our simulation efforts by cleaning up our existing CAD models for the system. This included selection of certain components that were not included in our original, simplified model. Specifically, component selection of fasteners, shaft keys, and retaining rings for the system was done.

We also started on some basic DFM considerations. This included making physically machinable parts. As seen in the comparison image below, the original CAD had a base plate with protruding supports which is infeasible to manufacture in any way. This was fine for an initial concept, but needed to be improved for more detailed plans. The original supports were replaced with supports that could be screwed into the base plate.

|             **Original CAD**              |              **Updated CAD**              |
| :---------------------------------------: | :---------------------------------------: |
| !![Old supports](/images/wk4-cad-old.png) | !![New supports](/images/wk4-cad-new.png) |

Other DFM considerations that were made were as follows:

- Threads need to be no longer than roughly 3 times the diameter of the major diameter
- No fillets can be at horizontal edges at the bottom of a machined hole, but fillets at vertical edges of a machined hole are required
- Breaking all exterior edges

It was great to get the mechanical simulation underway and we are looking forward to getting the models fully flushed out! Next steps will be using the CAD to develop a high quality animation and exploded view of the model, which will be used to demonstrate how the system would operate as a fully assembled, physical prototype.
