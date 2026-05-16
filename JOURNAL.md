---
title: "Toasterboard"
author: "Issac Liu"
description: "Open-source Breadboard Companion clone"
created_at: "2026-05-15"
---

# Hack Club Forge Journal

## May 15: Started work!

Spent today reverse-engineering the BBCIII and laying out the schematic.

Update: Actually, I found that the Breadboard Companion has publicly available schematics hosted on [their website](https://breadboardcompanion.com/projects-and-freebies)! They're really low-quality though, I can barely read it. 

!(Picture of low-quality schematic)[https://raw.githubusercontent.com/Camuise/toasterboard/refs/heads/main/assets/journal/may15-schematic.jpeg]

Change of plans, I'm first going to recreate the original BBCIII to the best of my ability using the schematic *before* I start making improvements to the design. I have two major gripes that I want to fix in the original design:
1. Barrel jack connector/ 9V battery. Very inconvenient to use, so plan is to swap to a USB-C port.
2. The board's overhang covers three whole rows of breadboard. Just plain bad.
3. Small ick: it's a little ugly in my opinion.

I might switch the through hole mounted components to SMD? We'll see. For now, I'm just focusing on getting an actually readable schematic.

Today so far I've added the voltage regulator, the 555 timer, and the Schmitt trigger. I've yet to finish wiring them up yet. What I have finished though, is wiring up the LEDs and DIP switches!

!(Schematic progress for today)[https://raw.githubusercontent.com/Camuise/toasterboard/refs/heads/main/assets/journal/may15-progress.jpeg]

**Total time spent: 3 hours**
