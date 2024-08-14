# DIY-Sim-Racing-FFB-Pedal-PCBs
This repository contains my PCB Designs for ChrGri/DIY-Sim-Racing-FFB-Pedal

I started building a Sim Racing pedal for my rig with a friend and realized fairly quickly that we wanted a PCB design different to the one that's part of the project. My main reasons for this are:
- Something more compact than the one included in the main hardware repository
- I also wanted to rely less on hobbyist parts (dev boards) and have something more built-for-purpose
- We wanted to to use USB-HID and something based on the ESP32-S3 allowed this (the ESP32 doesn't have native USB support)

Initially, the board was based on the ESP32-S3 module that Espressif offers. This is nice because it's already certified for commercial use, but it has one major downside - it requires the use of specially controlled temperatures during assembly. This can make it expensive to build, because you can't use economy PCBA services. Of course, if you're going to assemble these boards at home that doesn't matter but some SMT parts are not for the feint of heart - especially the smaller ones. Now it's based on the ESP32-S3 chip with 128Mb of SPI-flash, which mimics the ESP32-S3-WROOM(N16) module.

# Features
- Tiny size! It's just over 2" square (51mm x 51mm)
- ESP32-S3 based, so you can get USB-HID support out of the box and don't need to use Bluetooth or additional boards
- Dedicated connections for loadcell, servo serial, servo signal, an emergency cut-off button
- All headers are 2.54mm, meaning you can connect 'normal' pin headers, JST-XH connectors or just solder straight to the board, use screw terminals or use any other 2.54mm pitch connector
- Fully compatible with mainline release builds, you don't need any special firmware builds to use this PCB
- If you want to use Bluetooth or Wifi for any reason, a u.fl IPEX connector is included for an external antenna (useful if you pedal is aluminum)
- Dedicated switches for device selection (Gas/Brake/Clutch)
- USB-C connector for power and (when used) USB-HID
- UART out from the ESP32-S3 via an FTDI-compatible header

## A quick note on connectors
The board will ship without connectors installed - this reduces to the cost of the board (otherwise you need to pay a human at JLCPCB to install them) but also allows you to use whatever connector type you like, or solder straight to the board. This means that while the board comes assembled, you will need a soldering iron (or a friend with one) to be able to finish the board.

# Ordering the PCB
You can buy plain boards and assemble them yourself if you're a massachist. I've done it myself but I don't recommend it. Placing some of the devices, especially the ESP32-S3 IC are very tricky due to their size and how close the pins are. Only do this if you're really sure you can do it right! For most mortals, get the PCB assembled professionaly by a robot that's better at this than we are.

1. Go to the `ESP32-S3` folder and download the gerber, BOM and pick-and-place files. These are what you need to order the PCBs fully assembled from JLCPCB.
2. Head over to [JLCPCB](https://jlcpcb.com/quote) and click on "Add gerber file" and select the gerber zip file you downloaded from this repo
You can select the number of PCBs to order. The miniumum is 5, then it's increments of 5. If you want to change the color of the PCB, now's the time! JLCPCB offers green, purple, yellow, black, blue, red and white. If you don't change anything, you'll get green (the fastest).
![Upload a gerber file](images/ordering/1-add-gerber.png)
3. The website will process the file and you should see the PCB appear. Scroll down to `PCB Assembly` and enable the option. Then make sure you get the number of boards you want to have assembled. You can get all 5 if you need. If you need fewer, you can also order two. It's cheapest when you order in bulk, so you can always ask in the Discord channel if lots of people want to buy, because then it's cheaper (although someone has to ship them all out!)
![Enable PCB Assembly](images/ordering//3-select-pcba.png)
Now click "Next". You will need to sign in or create an account to continue.
4. You'll see a picture of the PCB (step 1). Just click `Next`, there's nothing to do here.
5. Next you'll need to upload the BOM and pick-and-place files you downloaded. Click on the `Process` button
6. The next screen will show you all the parts in the BOM and confirm the quantity of each. If stock is low or there isn't any stock of some parts then you will be notified. You will need to find a compatible part. Feel free to ask on the PCBA channel on the Discord server if you don't know how to find a part. Don't use the recommended replacements in the window, they're often the wrong size!
Click Next
7. Finally, you will be given a summary and you can click `Save to cart`. Now it's like checking out anywhere else, you don't need my help for that!

# Questions?
Come ask on [the PCBA channel on the Discord server](https://discordapp.com/channels/1113129142142120159/1269625529334628373).