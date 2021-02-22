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

We were able to get the base construction complete including wiring for the controller, shield, vacuum pump, ultrasonic sensor, and power system. In addition to the base assembly, we integrated a push button to start the process of lifting the dish lid with the suction mechanism and an LED used for error signaling. Both of these peripherals required appropriately specced pull-down resistors.

The following two images show the updated system construction:

![Suction overview](/images/wk3-suction-overview.jpg)

![Suction wiring](/images/wk3-suction-wiring.jpg)

### Testing

After the initial construction of the system was complete, the next step was performing the relevant system tests.

The ultrasonic sensor being used to detect the success of lifting and replacing the lid on the Petri dish had to be characterized before the system could operate as intended.

![Suction cup and dish](/images/wk3-suction-cupanddish.jpg)

The conclusions from this characterization were that the sensor behaves linearly and has suitable accuracy over a reasonable use range, as described by the following graph:

![Sensor graph](/images/482-sensor-graph.jpg)
(Note: the sensor is not rated for distances less than 2cm)

Once the ultrasonic sensor was tested, the suction mechanism could be physical tested. The following video demonstrates the current operation of the suction mechanism. As you can see, the pump responds to the push button input, allowing the lid to be removed from the dish, and turns off after an appropriate wait time.

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

#### Alignment and initial attachment error

![Suction error](https://media.giphy.com/media/ymYyspDihJIDFyxg82/giphy.gif)

#### Forcing the lid off mid-process

![Suction error forced](https://media.giphy.com/media/6hRtBTwRIiMeW9G2dC/giphy.gif)

Overall, this was an exciting week for progress on the suction mechanism. Next steps will be modifying and improving the system layout and characterizing the suction mechanism to ensure optimal performance.

## Mechanical Simulation: Initial Updates

... Coming soon
