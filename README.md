# N64RGBv1-Integrated-3.3v-Regulator

This is a derivative of Borti4938's N64RGBv1 project. The layout of the board is fundamentally the same, but a 3.3v LDO regulator has been added to the PCB layout to help clean up the image quality issues that the N64RGBv1 has when in stock form. 

This is a hardware only dirivative of the N64RGBv1 project, it uses the stock N64RGBv1 firmware provided by Borti4938.  

# Features
- Support for different CPLDs on a common PCB design:
  * MaxII EPM240T100C5
  * MaxII EPM570T100C5
  This PCB does not support MAX V CPLDs.
  
# Changes compared to N64RGBv1
- Removed Compoenets:
  * Pads for U3, C31, C32 have been removed, thus removing support for MAX V CPLDs
  * VCC pad removed.
- Layout Changes:
  * Ctrl and Rst pads shrunk and relocated to the left side of the PCB to match 1.27mm pitch ribbon cable spacing. 
  * Left side GND pad shrunk and relocated to match 1.27mm pitch ribbon cable spacing.
  * GND, CS#, BLUE, GREEN, RED, and CS75# pads shrunk and relocated to match 1.27mm pitch ribbon cable spacing.
- Added Components:
  * U3 is a 3.3v LDO regulator SOT223 footprint. Recommended part is NCP1117ST33T3G
  * C4, C5 10uF ceramic capacitors in 0805 footprint. Recommended part is GRM21BR60J106ME19L
  * C6 2.2uF ceramic capacitor in 0603 foorprint. Recommended part is CL10A225KO8NNNC
