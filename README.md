# The Study Buddy
---
Alternatively, the Anti-procrastination device.

For my Unix final, I kitbashed a little machine that when powered, lights up and beeps incecently when you walk away from it. It will keep making noise until you come back and hit the button to turn it off. Theoretically preventing someone from leaving their workspace absentmindedly.   
---
**You will need:**
- 1x Raspberry PI
- 1x Breadboard
- 1x Button
- 1x LED
- 3x Appropriate resistors
- 6x Female to Male jumper cables
- 1x Male to Male jumper cable
- 1x distance sensor
- IDE or console of your choice
 
**Included with these instructions:**
- code.py
- beep.wav

  ---
 
Here's the schematic:
![schematic](https://github.com/user-attachments/assets/0db77615-2b40-4e9f-966e-f675e348412e)

## Step 1.

Connect the distance sensor to the Pi like so. Make sure the resistors are properly seated, or else you could burn out the sensor.

---

## Step 2.

Connect the LED to the Pi.

---

## Step 3.

Connect the button, note the connections.

## Step 4.

Load beep.wav and code.py onto the PI, making sure to keep both in the same folder. Then, run code.py. 

If done properly, the device will beep when you walk away, and not stop until silenced. yay.

---

Attribution:
**Gpiozero: **
https://gpiozero.readthedocs.io/en/stable/recipes.html#distance-sensor
-Build inspiration




---
