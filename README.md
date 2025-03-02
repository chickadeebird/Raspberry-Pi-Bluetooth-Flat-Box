# Raspberry Pi Bluetooth Flat Box
A Raspberry Pi Bluetooth Flat Box for use in calibrating astrophotography images.

# Introduction
This is a set of DIY directions for the creation of a flat box used in amateur astrophotography. This includes the ASCOM device drivers, bluetooth server, and general instructions for the complete flat box. This project has its origins in an ongoing problem I have with a residual artifact in my images after flat correction with an LED pulse width modulation (PWM) flat box light. This was created to solve two problems:

* uneven flat box illumination
* artifacts stemming from the PWM

I believe there is a significant improvement in the quality of my final images, but the artifact problem still remains.

I might also suggest that this can be created without any soldering or complicated electronics. It does involve some software installation on the raspberry pi's Linux operating system, but I have done my best to document the steps I took to get it working.

### Compatibility
This systems works with acquisition software that runs on Windows only. I may consider creating an Alpaca-based ASCOM driver for it to be platform-independent, but I would have no way to test it other than on a Windows-based system. Let me know if there is significant interest in a platform-independent solution.

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
* The bluetooth server that runs on the raspberry pi is available in another of my repositories https://github.com/chickadeebird/RaspPiGATTServer

The raspberry pi bluetooth server link has full instructions on installation.
