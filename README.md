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

Here's the code: 

`
import pygame
from gpiozero import DistanceSensor, LED, Button 
from signal import pause
from time import sleep

pygame.mixer.init()
pygame.mixer.music.load("beep.wav")

light = LED(17)
button = Button(2)
sensor = DistanceSensor(23, 24)

beeping = False

def beepstop():
	global beeping
	if beeping:
		beeping = False
		pygame.mixer.music.stop()
		light.off()
		
def beepstart():		
	global beeping
	if not beeping:
		beeping = True
		pygame.mixer.music.play(-1)
		light.on()

sensor.when_in_range = beepstart
button.when_pressed = beepstop

pause()

`

  ---
 
Here's the schematic:
![schematic](https://github.com/user-attachments/assets/0db77615-2b40-4e9f-966e-f675e348412e)

## Step 1.

Connect the distance sensor to the Pi like so. Make sure the resistors are properly seated, or else you could burn out the sensor. I chose to plug the sensor right to the breadboard because I ran out of jumpers. 

![image](https://github.com/user-attachments/assets/8c2baa87-85ba-4115-93a7-f914c4e60a12)

---

## Step 2.

Connect the button, note the connections.

![image](https://github.com/user-attachments/assets/c9634c49-c224-4f23-a5f5-b63df69dd862)

---

## Step 3.

Connect the LED to the Pi.

![image](https://github.com/user-attachments/assets/fc9eaef0-74fe-4b57-871e-3a7435e527e6)


## Step 4.

Load beep.wav and code.py onto the PI, making sure to keep both in the same folder. Then, run code.py. 

If done properly, the device will beep when you walk away, and not stop until silenced. yay.

![image](https://github.com/user-attachments/assets/a15882ae-5b82-4f3e-b760-5048e8ee346d)


---

Attribution:
**Gpiozero: **
https://gpiozero.readthedocs.io/en/stable/recipes.html#distance-sensor
-Build inspiration




---
