---
title: "Toasterboard"
author: "Issac Liu"
description: "Open-source Breadboard Companion clone"
created_at: "2026-05-15"
---

# May 15: Started work!

Spent today reverse-engineering the BBCIII and laying out the schematic.

Update: Actually, I found that the Breadboard Companion has publicly available schematics hosted on [their website](https://breadboardcompanion.com/projects-and-freebies)! They're really low-quality though, I can barely read it. 

![Picture of low-quality schematic](https://raw.githubusercontent.com/Camuise/toasterboard/refs/heads/main/assets/journal/may15-schematic.png)

Change of plans, I'm first going to recreate the original BBCIII to the best of my ability using the schematic *before* I start making improvements to the design. I have two major gripes that I want to fix in the original design:
1. Barrel jack connector/ 9V battery. Very inconvenient to use, so plan is to swap to a USB-C port.
2. The board's overhang covers three whole rows of breadboard. Just plain bad.
3. Small ick: it's a little ugly in my opinion.

I might switch the through hole mounted components to SMD? We'll see. For now, I'm just focusing on getting an actually readable schematic.

Today so far I've added the voltage regulator, the 555 timer, and the Schmitt trigger. I've yet to finish wiring them up yet. What I have finished though, is wiring up the LEDs and DIP switches!

![Schematic progress for today](https://raw.githubusercontent.com/Camuise/toasterboard/refs/heads/main/assets/journal/may15-progress.png)

**Total time spent: 3 hours**

# May 16: Continuing the schematic

I think the schematic is finished now? I spent a lot of time on figuring out what footprints to assign, but now it's complete? I just have to add the power input plugs.

![Finished schematic](https://raw.githubusercontent.com/Camuise/toasterboard/refs/heads/main/assets/journal/may16-schematic.png)
![Finished PCB](https://raw.githubusercontent.com/Camuise/toasterboard/refs/heads/main/assets/journal/may16-pcb.png)
![3D preview of PCB](https://raw.githubusercontent.com/Camuise/toasterboard/refs/heads/main/assets/journal/may16-3d.png)

**Time spent: 2 hours**

I added the power plugs, with some help from Google Gemini to figure out how to handle multiple power input sources properly (obligatory chat link for the [USB-C port](https://t3.chat/share/x91vfc2y4v) and the [barrel jack](https://t3.chat/share/xf3eg8aq73)). In addition, I added a switch so the user can swap between the two power inputs I'm providing.

![Completed power circuit](https://raw.githubusercontent.com/Camuise/toasterboard/refs/heads/main/assets/journal/may16-pwr.png)

I also finished routing everything!

![Routed PCB](https://raw.githubusercontent.com/Camuise/toasterboard/refs/heads/main/assets/journal/may16-routedPCB.png)

**Time spent: 8 hours**

**Total time spent: 10 hours**
