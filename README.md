# DIY-Sim-Racing-FFB-Pedal-PCBs
This repository contains my PCB Designs for ChrGri/DIY-Sim-Racing-FFB-Pedal

Most of my PCB designs are custom-built for the DIY Force Feedback Pedal, and probably aren't really useful for anything else. Most of the boards are designed to be bought fully assembled by a PCBA company - my files should all work at JLCPCB.

Initially, this repository contains files for my ESP32-S3-based pedal control board. Later I will add a power board and a bridge board, and maybe some other stuff (like an ESP32-based controller board or a variant with USB-C instead of USB-B).

# Ordering the PCBs
You can buy plain boards and assemble them yourself if you're a massachist. I've done it myself but I don't recommend it. Placing some of the devices, especially the ESP32-S3 IC are very tricky due to their size and how close the pins are. Only do this if you're really sure you can do it right! For most mortals, get the PCB assembled professionaly by a robot that's better at this than we are.

1. Download the gerber, BOM and pick-and-place files. These are what you need to order the PCBs fully assembled from JLCPCB.
2. Head over to [JLCPCB](https://jlcpcb.com/quote) and click on "Add gerber file" and select the gerber zip file you downloaded from this repo
You can select the number of PCBs to order. The miniumum is 5, then it's increments of 5. If you want to change the color of the PCB, now's the time! JLCPCB offers green, purple, yellow, black, blue, red and white. If you don't change anything, you'll get green (the fastest).
![Upload a gerber file](images/ordering/1-add-gerber.png)
3. The website will process the file and you should see the PCB appear. Scroll down to `PCB Assembly` and enable the option. Then make sure you get the number of boards you want to have assembled. You can get all 5 if you need. If you need fewer, you can also order two. It's cheapest when you order in bulk, so you can always ask in the Discord channel if lots of people want to buy, because then it's cheaper (although someone has to ship them all out!)
![Enable PCB Assembly](images/ordering//3-select-pcba.png)
Now click `Next`. You will need to sign in or create an account to continue.
4. You'll see a picture of the PCB (step 1). Just click `Next`, there's nothing to do here.
5. Next you'll need to upload the BOM and pick-and-place files you downloaded. Click on the `Process` button
6. The next screen will show you all the parts in the BOM and confirm the quantity of each. If stock is low or there isn't any stock of some parts then you will be notified. You will need to find a compatible part. Feel free to ask on the PCBA channel on the Discord server if you don't know how to find a part. Don't use the recommended replacements in the window, they're often the wrong size!
Click `Next`
7. Finally, you will be given a summary and you can click `Save to cart`. Now it's like checking out anywhere else, you don't need my help for that!

# Questions?
Come ask on [the PCBA channel on the Discord server](https://discordapp.com/channels/1113129142142120159/1269625529334628373).