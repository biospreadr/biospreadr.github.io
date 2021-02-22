---
title: "Kicking things off, ordering parts, and 3D printing"
date: 2021-01-31
image: "images/481_full_design.png"
# author
author: ["Biospreadr Team"]
# categories
categories: ["Weekly updates"]
tags: ["update"]
# meta description
description: "Kicking things off, ordering parts, and 3D printing"
# save as draft
draft: false
---

# Welcome!

This is our first blog post out of many that will be coming over the next few months. We'll be documenting our progress as we implement the designs we created last term for our automated sample preparation device, **BioSpreadr**. Included in the posts will be updates on the building, testing, and development of the project. We'll document the major challenges we're facing, significant breakthroughs that happen during development, and anything else that might be interesting! Thanks for tuning in :)

# Weeks 1-3

Over the first weeks of the term the team focused on getting organized, setting up the BioSpreadr website, checking in with our project supervisors, ordering parts, and beginning the development of the carrier tube component. All parts were procured from either McMaster-Carr, DigiKey, or the personal supply of team members. These two external suppliers were chosen for their reliability, fast shipping times, and excellent selection of products which fulfilled all our project needs.

The project management tasks included establishing how work would be divided amongst group members, creating a timeline of when we expect/want to get project milestones completed by, and deciding how we would manage the purchasing of components and materials.

The final breakdown of team responsibilities was based on geographic location:

- Emil & Maddie will work on the carrier tube assembly in Waterloo
- Nik will work on the suction mechanism in Hamilton
- Chris will work on detailed mechanical simulation (CAD, DFM, fluid analysis) in Halifax

Overall, this initial preparation phase was successful and all our team members are in a good position to start implementing and testing our designs. Because the body of the carrier tube assembly is 3D printed, we could kick off the build phase for this part before the suction mechanism which will be started next week.

## Carrier Tube: Mechanical Assembly

Work on the carrier tube began with the rental of a 3D printer from a friend. It took some time to get acquainted with the printer, specifically with axes calibration (XYZ), levelling of the bed, and fine-tuning the Z level of the extruder. Overall, this process took several days, and many prints were botched during the process (as can be seen in the following photos).

![Carrier Tube (1)](/images/wk1-carrier-tube-busted1.jpg)

![Carrier Tube (2)](/images/wk1-carrier-tube-busted2.jpg)

![Carrier Tube (3)](/images/wk1-carrier-tube-busted3.jpg)

Getting high-quality prints from a 3D printer isn't a matter of just opening the CAD model and pressing Ctrl+P, there is quite a bit that has to be taken into account.
Even mundane things like airflow and air temperature around the printer can completely ruin the print and cost hours of progress.

Eventually after many failed prints, the main body of the carrier tube and the tube itself were printed. By this time, parts from McMaster-Carr were received and test fits of everything could be conducted. Some sanding of the reservoir tube was required, as well as the addition of some lead-in chamfers to assist in the fit. These manual improvements will be added to the CAD. Additionally, some support material was removed from the various holes of the parts to assist in the dowel and Delrin bead fit. The following photos show a screenshot of the printer configuration, the setup used during this process, and the improved mechanical components of the carrier tube.

![Carrier Tube (4)](/images/wk1-carrier-tube-1.png)

![Carrier Tube (5)](/images/wk1-carrier-tube-2.jpg)

![Carrier Tube (6)](/images/wk1-carrier-tube-3.jpg)

The Delrin beads pass through the parts without any problems and the feed tubes have a nice fit as well.
Overall the 3D printing process is well suited to this type of design, given that it is relatively consistent (once it is fine tuned) and provides acceptable quality.

The next steps for the carrier tube assembly are the addition of the solenoid and system integration of the mechanical carrier tube components with the electronics and software. We'll also be starting on the other elements of the project soon, so stay tuned to stay up to date with BioSpreadr's progress!
