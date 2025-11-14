# SLWF-01pro-AUX-AC-Firmware
Esphome yaml entry for SLWF-01pro (v1.1) for operating an AUX AC unit (or Yitahome).

Mostly taken from https://github.com/GrKoR/esphome_aux_ac_component

Wanted to publicize my version for people looking to get their SLWF-01pro modules working with AUX AC units. 

Originally I had a Mr. Cool unit with the stock firmware of the SLWF-01pro v1.1, but that unit died and I replaced it with the cheapest unit that I could find with wifi (Yitahome 120V 12k BTU). I was able to modify the yaml from the above repo and provide a working version for this specific esp module. The key is the pinout, tx and rx. I don't have a v2.1 to try unfortunately. I was able to use the instructions below to flash the 1.1 module with my compiled yaml (esphome compile XXX.yaml) and then upload it to the device using the CH340 usb to uart converter. 

This is where I got my unit which came with a generic broadcom wifi dongle. Simply replaced it and all is well:

https://www.yitahome.com/products/12000-btu-20-seer2-ductless-mini-split-air-conditioner-110v-p-7267.html?req_t=7267

See this page for flashing firmware (https://smartlight.me/diy-smart-home/slwf01_flashing_en):

I am also archiving it here in case it ever disappears from that site. All credit goes to smartlight for these below instructions:

Flashing device version 1.1 or 1.2:

Prepare:
1. For flashing you need usb-ttl on CH340G or cp210x chip

2. Download and install the driver for your converter CP210x  CH340G

3. Download and extract the firmware slwf01pro download

4. Download the flasher program https://github.com/esphome/esphome-flasher/releases

5. Connect slwf01pro to usb-ttl according to the diagram:

CH340
<img width="1280" height="960" alt="image" src="https://github.com/user-attachments/assets/ddc7aff1-5666-45de-98e7-d70380bbbe70" />
CP210x
<img width="1280" height="960" alt="image" src="https://github.com/user-attachments/assets/9370156e-a851-4850-831d-40b076dd56dc" />





Flashing:

1. Hold button FLH on slwf01 DO NOT RELEASE THE BUTTON UNTIL THE FLASHING STARTS

2. While holding down FLH, connect usb-ttl to USB

3. Open the flasher program
   
<img width="709" height="642" alt="image" src="https://github.com/user-attachments/assets/cb82c7d1-9107-4fb5-8d5d-b5cd02d8c162" />


4.1 Select an available COM port

4.2 Select the unzipped .bin firmware file

4.3 Press the Flash button

4.4 If the flashing has not started, then disconnect the device and insert it again into USB with the FLH button pressed

*After the flashing starts, you can release the FLH button

4.5 Wait for the message about the successful flashing

5. Your slwf01 is ready to use, unplug it from usb-ttl and plug it into your air conditioner. The module needs to be reconnected to your network.

Flashing device version 2.1:

1. Go to https://smlight.tech/flasher/#slwf01proV2

2. Hold "FLH" button on the device

3. Connect the device to the PC via the Type-c connector and release the "FLH" button after connecting the device to the PC

4. Select the firmware version and press the "Flash" button

If flashing has not started, then go back to step 2 and start try again.

