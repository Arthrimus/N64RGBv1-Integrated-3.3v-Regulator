# N64RGBv1-Integrated-3.3v-Regulator

This is a derivative of Borti4938's N64RGBv1 project. The layout of the board is fundamentally the same, but a 3.3v LDO regulator has been added to the PCB layout to help clean up the image quality issues that the N64RGBv1 has when in stock form. 

This is a hardware only derivative of the N64RGBv1 project, it uses the stock N64RGBv1 firmware provided by Borti4938.  

### Features
- Support for different CPLDs on a common PCB design:
  * MaxII EPM240T100C5
  * MaxII EPM570T100C5
  This PCB does not support MAX V CPLDs.
  
### Changes compared to N64RGBv1
- Removed Components:
  * Pads for U3, C31, C32 have been removed, thus removing support for MAX V CPLDs
  * VCC pad removed.
- Layout Changes:
  * Ctrl and Rst pads shrunk and relocated to the left side of the PCB to match 1.27mm pitch ribbon cable spacing. 
  * Left side GND pad shrunk and relocated to match 1.27mm pitch ribbon cable spacing.
  * GND, CS#, BLUE, GREEN, RED, and CS75# pads shrunk and relocated to match 1.27mm pitch ribbon cable spacing.
- Added Components:
  * U3 is a 3.3v LDO regulator SOT223 footprint. Recommended part is NCP1117ST33T3G
  * C4, C5 10uF ceramic capacitors in 0805 footprint. Recommended part is GRM21BR60J106ME19L
  * C6 2.2uF ceramic capacitor in 0603 footprint. Recommended part is CL10A225KO8NNNC
  * Added +12v input pad.
  
### MAV NUS adapter changes
- shrank and relocated VCC and GND pads to align witht he rest of the pads on the adapter, spaced to match 1.27mm pitch ribbon cable.
  
### How to build
- Have the PCB files manufactured by your preferred PCB maker, or use the [OSHpark link](https://oshpark.com/shared_projects/rxFdHPg6)
- Source components from the BOM file
- Assemble your PCB
- Flash the firmware to the PCB
  * You need an Altera USB Blaster (USB Blaster clones should work) 
  * The board needs to be powered externally while flashing. You could install the board into the N64 before programming and use the N64 to power the board while flashing. 
- Install the board to your N64
  * Installation instructions are provided in Borti4938's guide [here](https://github.com/borti4938/n64rgb/blob/master/Guide_N64A_n_N64RGB.pdf). I have also recorded an installation video for this mod which you can watch on my youtube channel [here](https://youtu.be/NxGIhH4mSoI?t=592)
  * The only significant difference for the installation process compared to the guide is that you do not connect 3.3v power from the N64 to the modding board. Instead you connect +12v power from one of the +12v sources on the N64 motherboard to the pad labeled +12v on the modding board.
  * Check the pinout of the video encoder in your N64.
  * If you have an AVDC-NUS or MAV-NUS encoder it is recommended that you use the MAV-NUS adapter PCB.

### Firmware
 - This project uses Borti4938's stock N64RGBv1 firmware located [here](https://github.com/borti4938/n64rgb/tree/master/generalRGBmod/firmware)
   * If you don't want to compile your own firmware files, you can use the compiled firmware file that matches your CPLD type [here](https://github.com/borti4938/n64rgb/tree/master/generalRGBmod/firmware/output_files/v1)
