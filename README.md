# Mini Linux Handheld Game Console

A custom-built 4-layer PCB handheld game console based on the Allwinner F1C200s SoC.

EASYEDA LINK-  https://oshwlab.com/satvikpockitce/project_wvjbfxpj

<img width="914" height="539" alt="image" src="https://github.com/user-attachments/assets/cc9e210a-58eb-4e11-9c0c-be9cb0d55673" />


## goal

The goal of this project is to build a small, low-cost, Linux-capable handheld that can run lightweight emulators and homebrew games using a fully custom PCB, display interface, controls, audio, storage, and power system.

it should be capable of running Linux and emulating classic systems such as:

- NES
- Game Boy / Game Boy Color
- Sega Master System
- Game Gear
- SNES
- Sega Genesis / Mega Drive
- PC Engine
- Neo Geo-class 2D systems, depending on software and memory limits

## processor

**Allwinner F1C200s**

The main processor used in this project is the **Allwinner F1C200s.**

Key specs:

CPU: ARM926EJ-S
Typical clock: around 420 MHz
Integrated RAM: 64 MB DDR1 inside the package
Display output: RGB / TTL LCD interface
Storage support: SD / MMC / SPI
Connectivity: USB OTG, UART, SPI, I2C

## Display
The console uses a 2.4-inch TFT LCD.

## Controls

Controls:

- A 
- B 
- X 
- Y 
- L1  
- R1  
- Start 
- Select 
- Digital joystick / D-pad using a 5-way switch

## Audio
The design uses the NS4150B audio amplifier.

Features:

- 3W mono Class-D amplifier
- Filterless output design
- easy to work with

## USB-C Ports

The console includes two USB-C ports.

### USB-C Port 1: Programming / UART

This USB-C port is used for serial communication and programming/debugging.

It uses a CH340N USB-to-UART chip to connect a computer to the F1C200s UART. (no ttl stuff needed)

### USB-C Port 2: USB host

Uses:

USB host functionality
External peripherals
Possible keyboard/controller support
General USB expansion

## power

Main rails:

- 3.3V
- 3.0V
- 2.5V
- 1.2V
- 5V battery/USB-VBUS rail

ICs used-
- 3 × SY8088 buck converters
- 1 × XC6206 LDO

## how to replicate
- Download the Handheldconsolelinux.epro2  and import it in easyeda pro (pro is free :D!!) 
- in the top you should see a export drop-down
- in there you can see export parts/bom to lcsc (now you can directly order all parts with adding them to your cart with a single click!)
- there would also be order from jlcpcb, which if you click you are directly sent to the order page with the correct design rules/gerbers uploaded

# changelog over time (DD-MM-YYYY)

## 06-05-2026

- project start

## 09-05-2026

- component research and basic ideation done

## 14-05-2026

- first schematic revision done

## 15-05-2026

Design notes for later fixes and to be kept in mind for routing-

- Integrated download circuitry eliminates the need for a TTL downloader when viewing serial port data; a standard A-to-C cable is sufficient.
Using the CH340N solution, which has a built-in crystal oscillator, requires few external components, and is small in size, it is simply too good to be true.

- The top-mounted FPC socket was changed to a bottom-mounted one.
Since the top-mounted design is only available in a drawer-style configuration and not a flip-top design, and the drawer-style base is easily pulled up along with the base when removing the screen, it is not recommended.

## 18-05-2026

- Fixed the issue of the NS4150B not working, users who have already installed version 2/28 are advised to connect a 5V network cable to pin 1 of the chip.

- Fixed the issue of the charging indicator light not lighting up (it was drawn backwards).

- Remove the charging status detection circuit (system not supported).

## 20-05-2026

#### final schematic complete, placement started

- The amplifier section was updated, the SD pin was replaced, and the IN- leakage issue that would cause the speaker to overheat and produce no sound was resolved.

- AGND is used as a ground plane, connected to the common ground via a 0-ohm resistor. I'm unsure if this improves noise levels.

## 23-05-2026

#### Placement complete
**todo**-

- Fixed button pin errors (ABXY positions are out of order)

- Fix button pin misalignment

- Fix the screen FPC socket position

## 25-05-2026

Placement errors fixed, routing started

## 02-06-2026

Initial first pass routing done, todo-

- fix tft filter routing

- complete the inner power layer copper region fills

- add copper pour regions on all layers

## 06-06-2026

Routing finally complete

## 10-06-2026

**Final project wide changes suggest by friends and some reddit dudes**

- Gerber generated, exported, BOM device standardization complete, ready to order

- shipped to hackclub's macondo program and is under review right now


# Disclaimer

This is a work-in-progress DIY hardware project.
The board has not been fully validated yet, and some design decisions may change after testing.

Use the design as a learning reference, not as a guaranteed production-ready circuit.


<img width="1333" height="691" alt="image" src="https://github.com/user-attachments/assets/59e3c1f1-66d3-4a8c-810a-4445f76c5fb7" />
<img width="1316" height="698" alt="image" src="https://github.com/user-attachments/assets/01b2f2e0-cc64-462c-8f93-45c1c6d5f803" />
<img width="1298" height="670" alt="image" src="https://github.com/user-attachments/assets/1b196b3b-64d4-40f0-a453-ba19c87b8a79" />
<img width="1299" height="659" alt="image" src="https://github.com/user-attachments/assets/52f8beb8-26a3-4938-b541-d91af8fa2414" />

<img width="1009" height="583" alt="image" src="https://github.com/user-attachments/assets/bb971a86-5049-4b7b-8152-ed8804f9b7ba" />
<img width="914" height="539" alt="image" src="https://github.com/user-attachments/assets/cc9e210a-58eb-4e11-9c0c-be9cb0d55673" />
<img width="1240" height="652" alt="image" src="https://github.com/user-attachments/assets/16b263b9-ce0e-4dbf-9a40-8f62ca1db01c" />
<img width="1218" height="324" alt="image" src="https://github.com/user-attachments/assets/c5c5ca5c-0d50-4a71-a44a-9fda7afa5bba" />
