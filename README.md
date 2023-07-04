
# Monoprice Select Mini V2

You can find this file on [htpps://github.com/henkjannl/Monoprice](htpps://github.com/henkjannl/Monoprice). Potentially you need to make a Github account to doanload files, but that suold not be hard.

This repository contains some files for the monoprice select mini V2 3D printer

The printer is very simple: 
* It can print objects up to 120x120x120 mm. 
* The maximum nozzle temperature is 260°C
* The maximum bed temperature is 60°C
* The maximum print speed is around 55 mm/s

A good website about the printer is [https://mpselectmini.com/start](https://mpselectmini.com/start). It contains many useful links.

The printer is a direct clone from the Malayan M200 printer. I am including the user manual from this printer as pdf [here](.//m200_v2%20user%20manual.pdf). The user manual mentions WiFi but this is optional, this printer does not have WiFi `:sob:`



# SD card problem and workaround

A problem with this particular printer that I encountered is that it does not recognize the SD card. This is annoying since normally this is the simplest way to transfer files to the printer.

A workaround is to print via micro USB cable. This requires the printer to be connected to a computer until the print job is finished.

One way to send a print job to the printer using a USB cable is to use Pronterface. When you install [PrusaSlicer](https://www.prusa3d.com/page/prusaslicer_424/), you can choose to install Pronterface as a separate tool.

When plugging in the USB cable of the printer, you can use Windows Device Manager (press windows key, then type device, and choose Device Manager) to check to which COM port the printer is connected. You can use this COM port in Pronterface.

In Pronterface, you can open a .gcode file and send it to the printer.

I am including a working .gcode file [/Vaseline potje/Vaseline.gcode](./Vaseline%20potje/Vaseline.gcode). I printed this yesterday and it came out well.



# Potential upgrade: Octoprint

To prevent having your computer connected all the time, it is potentially a good idea to connect the printer to a Raspberry Pi and install [Octaprint](https://octoprint.org/). Personally I don't have experience with Octaprint, but it is used a lot by the open source community. It allows you to send files to the printer over WiFi, and even lets you connect a camera to the Raspberry Pi to monitor what the printer is doing. If you see something goes wrong you can then stop the printer using your phone. But you need to inves something in a Raspberry Pi (and maybe a compatible webcam).



# Potential repair

If you want to resolve the issue with the SD card, you could try the following things:
1. Potentially, the printer cannot communicate with SDHC micro SD cards, and you need an older micro-SD card which is not HC. But maybe this is not the problem and investing in such an SD card is then a waste of money. I don't remember which card I used when the printer was still working well.
1. Potentially, it may help to upgrade the embedded software of the main board, but I don't know what the currently installed version is, and where you can find a newer version. This incurrs a risk that something goes wrong an you cannot go back to the current state.
1. It may be possible to order a new main board as a spare part online. This ([https://gigdigit.com/mainboard-select-mini-v1-v2-new-quiet-version/](https://gigdigit.com/mainboard-select-mini-v1-v2-new-quiet-version/)) is the board that is currently in the printer, but there may be cheaper offerings for this board on other websites.

In all cases, please make a good decision if you want to spend the money. This printer was originally € 200 but that was a few years ago. New printers typically have more options and a larger build volume. The Octoprint option may then be better, since it will still retain its value if you have money for a new printer.



# Printing material 
I have only used the printer for PLA. 

A problem that I encountered is that the printed object is sometimes hard to remove from the print bed. The risk is then that you need to use a tool, which can damage the print bed. I therefore started using Kapton tape on top of the print bed. I will provide a spool of Kapton. You don't need to exchange it very often. It is hard to replace it without wrinkles. You can clean the capton layer with IPA (contact spray) and tissue, but maybe regular dishwashing soap may also work.

Another problem is the first layer. 
* If the nozzle is too near the print bed, the material is squashed and the print job fails due to overextrusion. 
* If the nozzle is too far away from print bed, there is underextrusion and the part will come loose from the print bed before the print job is finished.

Please make yourself familiar with print bed alignment. The procedure is in the user manual.

I have sometimes had good results with using a raft under a print. Please check online how to add a raft in the slicer. There are many sources online.


# PrusaSlicer
 
The printer manual suggests using Cura as a slicer, but personally I am a fan of PrusaSlicer. Both will work fine, perhaps check out both before you make a decision.

If you use PrusaSlicer, you can download [Prusaslicer settings\Prusaslicer config bundle for Monoprice Select Mini V2.ini](Prusaslicer%20settings/Prusaslicer%20config%20bundle%20for%20Monoprice%20Select%20Mini%20V2.ini) in this repository to setup the slicer. Use File > Import > Import Config Bundle and select the file. This config currently supports only one layer height. You may need to fiddle with the file to also add other layer heights. This highly inluences the print time.


Enjoy!!