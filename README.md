# Raspberry Pi Bluetooth Flat Box
A Raspberry Pi Bluetooth Flat Box for use in calibrating astrophotography images.

# Introduction
This is a set of DIY directions for the creation of a flat box used in amateur astrophotography. This includes the ASCOM device drivers, bluetooth server, and general instructions for the complete flat box. This project has its origins in an ongoing problem I have with a residual artifact in my images after flat correction with an LED pulse width modulation (PWM) flat box light. This was created to solve two problems:

* uneven flat box illumination
* artifacts stemming from the PWM

I believe there is a significant improvement in the quality of my final images from the better flats, but the artifact problem still remains.

I might also suggest that this can be created without any soldering or complicated electronics. It does involve some software installation on the raspberry pi's Linux operating system, but I have done my best to document the steps I took to get it working.

### Compatibility
This systems works with acquisition software that runs on Windows only. I may consider creating an Alpaca-based ASCOM driver for it to be platform-independent, but I would have no way to test it other than on a Windows-based system. Let me know if there is significant interest in a platform-independent solution.

It is tested and works with:

* Sequence Generator Pro
* N.I.N.A.

# List of materials
This is a list of the hardware I used to create this flat box. I am not responsible for anyone else's purchase or design decisions, although it was fairly straightforward to assemble the parts and get it running.

### Hardware
* Raspberry pi. I have tested this on both the RPi 3B and 4B and it works on both. It also seems to work on a Pi Zero W 2, but it is incredibly slow. https://www.amazon.ca/dp/B07WRMR2CX
* Monitor. I have tested this on a small RPi-specific LCD monitor, an LED monitor harvested from an old laptop with a monitor driver hardware kit purchased on Ebay, and a standard 28" monitor. All seem to work acceptably. https://www.amazon.ca/dp/B08S3JYSZZ?
* SD card for the raspberry pi. I used a 32GB card. A smaller one may be possible, but I am not certain. https://www.amazon.ca/dp/B073JWXGNT
* Power cable for the raspberry pi.
* Power cable for the monitor.
* HDMI cable to connect the raspberry pi to the monitor.
* Hardware to mount the monitor to the telescope, or to the wall of the observatory.

### Software
* The Windows ASCOM driver is in this repository (listed above) https://github.com/chickadeebird/Raspberry-Pi-Bluetooth-Flat-Box/blob/main/ASCOM.BlueChickFlat.exe
* The bluetooth server that runs on the raspberry pi is available in another of my repositories with full instructions on installation https://github.com/chickadeebird/RaspPiGATTServer

# Assembly
The assembly instructions are generally as follows:

* Install the operating system on the raspberry pi as per https://github.com/chickadeebird/RaspPiGATTServer
* Install the bluetooth (GATT) server on the raspberr pi as per https://github.com/chickadeebird/RaspPiGATTServer
* Connect the raspberry pi to the LED or LCD monitor. I used the Sunfounder monitor as that we made specifically to house a raspberry pi and therefore only 1, 12V power cable was needed
* Install the ASCOM flat box driver (ASCOM.BlueChickFlat.exe) from this repository
* If this is to be attached to the telescope, create a mount system around the opening of the telescope for the monitor to sit in
* If this is to be attached to a wall, create a mount system to attach the monitor and raspberry pi to the wall

# Operation of the image acquisition software
The bluetooth server on the raspberry pi needs to be associated with the ASCOM flat driver the first time the flat panel is used. First, plug in the flat panel. The raspberry pi operating system should boot up and eventually, a blue screen with a bluetooth symbol should appear. The image acquisition software (NINA or SGP) should be started on the acquisition device. Chickadee's bluetooth flat panel should be selected in the flat panel dropdown. The device settings adjacent to the dropdown should be started (a gears icon in NINA or wrench icon in SGP - below) and the popup dialog will begin scanning for the bluetooth server on the raspberry pi. 
<br/>
<img src="./figs/SGPConfigFlatBox.png" text='ASCOM Driver Config' align=left />  <br/>
<br/>
<br/>
<br/>
<br/>
<br/>
<br/>
<br/>
<br/>
<br/>
<br/>
<br/>
<br/>
<br/>
<br/>
<br/>
<br/>
<br/>
<br/>
<br/>
<br/>
Once the MAC address appears in the list, select the MAC address of the raspberry pi and hit the 'Pair with selected device' button. This should only be required once, the first time the system is used.
<br/>
<br/>
<img src="./figs/BlueChickDriverConfig.png" text='ASCOM Driver Config' align=left />  <br/>
<br/>
<br/>
<br/>
<br/>
<br/>
<br/>
<br/>
<br/>
<br/>
<br/>
<br/>
<br/>
<br/>
<br/>
<br/>
<br/>
<br/>
<br/>
<br/>
<br/>
<br/>
<br/>
Once the device is 'paired', the device can be connected and the brightness modified by using the slider in SGP or the +/- or entry widgets in NINA. The display should change from the blue screeen to a grey screen and dim or brighten based on the input values.

For both NINA and SGP, the brightness can be configured for each filter. In SGP, this is configured in the Control panel > Filters tab > Setting button.

# Initial Prototype
I do not have access to a 3D printer at the moment - I only have access to cardboard, duct tape and some velcro. However, this prototype seems to work well functionally even though it looks like a 5 year old made it. Ideally, I would design and print out a system to hang the monitor/raspberry pi system onto a plumbing flange that was large enough for the outside of the dew shield, but it works very well at the moment with even illumination across the flat box, a quick startup with the raspberry pi 4B, and the programmable wireless illumination is very convenient and easy to use. Below are some images of the prototype. I left the cover off to show the connection to the raspberry pi, but the monitor comes with a cover and fan that conceals the raspberry pi.

<img src="./figs/FlatBoxFront.jpg" text='ASCOM Driver Config' align=left />  <br/>

<img src="./figs/FlatBoxBack.jpg" text='ASCOM Driver Config' align=left />  <br/>
