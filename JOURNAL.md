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

Some major points of my chats with Gemini that I thought were worth logging:

- Gemini suggested swapping the 74LS14 Schmitt trigger for a 74HC14, which is a more modern part. I went ahead and made the change and it shouldn't affect the functionality? Apparently it runs cooler, which would be nice.
- Gemini introduced me to and helped me implement a rectifier circuit for the barrel jack input, so that if the user accidentally plugs in a power supply with the wrong polarity, it won't damage the board.
- *Most importantly*, Gemini helped me figure out how to handle the power input switching between the USB-C port and the barrel jack. I was initially planning on using a simple SPDT switch to swap between the two power inputs, wired straight to VDC, but Gemini pointed out that I was running the 5V from the USB-C port through the voltage regulator, which would choke on the 5V input. The solution was to move the voltage regulator *before* the power input switch, so that the switch is swapping between the raw inputs instead of the regulated output. This way, the voltage regulator can handle both the variable (but hopefully 9V) input from the barrel jack and the 5V input from the USB-C port without issue.

I also finished routing everything!

![Routed PCB](https://raw.githubusercontent.com/Camuise/toasterboard/refs/heads/main/assets/journal/may16-routedPCB.png)

**Time spent: 8 hours**

**Total time spent: 10 hours**

# May 17: Making things prettier

I rounded off the corners of the board and added my little logo! I also moved some stuff around to compact things and now it's pretty much complete?

![Finished PCB](https://raw.githubusercontent.com/Camuise/toasterboard/refs/heads/main/assets/journal/may17-pcb.png)
![3D preview of finished PCB](https://raw.githubusercontent.com/Camuise/toasterboard/refs/heads/main/assets/journal/may17-3d.png)

**Time spent: 1 hour**

I decided that, while having a single standalone board is nice, it would be cool if it was also available in a shield form factor for Arduino UNO users. So that's what I did!

![Finished shield schematic](https://raw.githubusercontent.com/Camuise/toasterboard/refs/heads/main/assets/journal/may17-shield-schematic.png)
![Finished shield PCB](https://raw.githubusercontent.com/Camuise/toasterboard/refs/heads/main/assets/journal/may17-shield-pcb.png)
![3D preview of finished shield](https://raw.githubusercontent.com/Camuise/toasterboard/refs/heads/main/assets/journal/may17-shield-3d.png)

**Time spent: 2 hours**

I realized that I forgot to label the pins on both the standalone and shield versions, so I went back and added labels to all the pins. I did the shield version first as I had it open already from the last journal entry.

![Labeled shield PCB](https://raw.githubusercontent.com/Camuise/toasterboard/refs/heads/main/assets/journal/may17-labeled-shield-pcb.png)

I also remembered that the Arduino R4 WiFi (my preferred Arduino board) doesn't have I2C pull-up resistors built in, so I added some 5.1k pull-up resistors to the I2C lines.

![Pull-up resistor schematic](https://raw.githubusercontent.com/Camuise/toasterboard/refs/heads/main/assets/journal/may17-pullups.png)

Then I went back and added the labels to the standalone version:

![Labeled standalone PCB](https://raw.githubusercontent.com/Camuise/toasterboard/refs/heads/main/assets/journal/may17-labeled-standalone.png)

I also added labels to the standalone version and shield version PCBs that indicate the different types of board.

![Labeled standalone PCB text](https://raw.githubusercontent.com/Camuise/toasterboard/refs/heads/main/assets/journal/may17-standalone-text.png)
![Labeled shield PCB text](https://raw.githubusercontent.com/Camuise/toasterboard/refs/heads/main/assets/journal/may17-shield-text.png)

Somehow I forgot that for a shield to still allow pass-through access to the Arduino's pins, I have to have headers on the top of the shield. So I added those in and labeled them as well. And that the bottom should be pins, not headers.

![Pins on shield](https://raw.githubusercontent.com/Camuise/toasterboard/refs/heads/main/assets/journal/may17-pins.png)

**Time spent: 1 hour**

**Total time spent: 4 hours**