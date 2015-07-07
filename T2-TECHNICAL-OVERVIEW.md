# Tessel 2 Technical Overview
This guide is intended to help code contributors understand how relevant system components of Tessel 2 work, where to find code and design files, and accelerate the development process through technical transparency. 
- [T2 Github Repositories](#relevant-github-repositories)
    - [Core](#tessel-2-core-repos-) 
        - [Command Line Interface](#-tessel-2-command-line-interface-https-www-github-com-tessel-t2-cli-cli-) 
        - [OpenWRT OS](#-tessel-2-operation-system-openwrt-https-www-github-com-tessel-openwrt-tessel-)
        - [Co-processor Firmware](#-tessel-2-co-processor-firmware-https-www-github-com-tessel-t2-firmware-)
    - [Tools](#tessel-2-tools)
        - [Virtual Machine](#-tessel-2-virtual-machine-https-www-github-com-tessel-t2-vm-vm-)
        - [Binary Compiler](#-tessel-2-compiler-https-www-github-com-tessel-t2-compiler-)
    - [Hardware Designs](#hardware-designs)
        - [Tessel 2 Hardware Design Files](#-tessel-2-hardware-design-files-https-www-github-com-tessel-t2-hardware-)
        - [Tessel 2 Parts Library](#-tessel-parts-library-https-github-com-tessel-tm-kicad-library-)
    - [Modules](#modules)
- [System Architecture](#system-architecture)
    - [Hardware Overview](#high-level-look-at-hardware)
    - [Software Overview](#software-architecture)
- [Code Deploy Walkthrough](#a-code-deploy-example)
- [Getting Questions Answered](#questions-)
- [Links to more information](#more-useful-links)

## Relevant Github Repositories

###Tessel 2 Core Repos:
You can find all of the Tessel repositories [on the organization page](https://github.com/tessel/) but this section provides some guidance over relevant Tessel 2-specific repositories.

#####[Tessel 2 Command Line Interface](https://www.github.com/tessel/t2-cli) (CLI)

The CLI is the primary method of interacting with Tessel for users and develoeprs. It provides useful functions like listing available Tessels, deploying code, and setting wifi credentials on the device.

#####[Tessel 2 Operation System (OpenWRT)](https://www.github.com/tessel/openwrt-tessel)
The primary processor of the Tessel 2 runs a very lightweight version of Linux called OpenWRT. OpenWRT provides all of the TCP/IP drivers, threading/schedule support, and runs Node, Rust or whatever other language you're using with Tessel 2. This repo contains all of the source files of the Tessel build of OpenWRT.

#####[Tessel 2 Co-processor Firmware](https://www.github.com/tessel/t2-firmware)
Tessel 2 features a SAMD21 co-processor that manages a handful of responsibilities like routing USB communication from the CLI and the realtime operations on the GPIO pins of the two module ports. This repo contains not only the firmware that drives this microcontroller but hardware-related scripts that define the interface to other languages (like [tessel.js](https://www.github.com/tessel/t2-firmware/node/tessel.js) for Node scripts) so that the available hardware functionality doesn't get out of sync with what is exposed to the OpenWRT processor.

    
### Tessel 2 Tools
#####[Tessel 2 Virtual Machine](https://www.github.com/tessel/t2-vm) (VM)
The VM is used primarily by Tessel developers who either don't have hardware available or want to develop on a faster computer. The repo provides the ability to create and run these Tessel virtual machines. You can use the CLI (see above) to interact with the running VM just as you would an actual Tessel 2. The VM has the limitation of not being able to set wifi credentials (it passes through the host network interface). It is not able to use 10-pin hardware modules but USB devices do get passed through.

#####[Tessel 2 Compiler](https://www.github.com/tessel/t2-compiler)
The Tessel 2 compiler is another virtual machine with all the build tools needed to develop [native add-ons](https://nodejs.org/api/addons.html) to Node modules. These add-ons are built to perform faster or interact with lower level hardware than JS alone would provide. The compiler is being used, for example, to develop the [audio-video Node module](https://github.com/tessel/node-audiovideo) for webcams and recording audio from microphones.

### Hardware Designs
#####[Tessel 2 Hardware Design Files](https://www.github.com/tessel/t2-hardware)
These are the production schematic and assembly files for the Tessel 2 hardware. You can find information about the parts that are used and how they are all connected to each other. These files were created with [KiCad](http://www.kicad-pcb.org/display/KICAD/KiCad+EDA+Software+Suite), a completely open source electronics design tool.
#####[Tessel Parts Library](https://github.com/tessel/tm-kicad-library)
This repo contains all of the KiCad part models for all Tessel hardware (not just Tessel 2). You will need this library in order to recreate the schematic and PCB of the hardware design files above.

### Modules

##### 10-Pin Modules
There are 9 compatible 10-pin hardware modules for Tessel 2 available at the time of this writing. Each of these modules have a repo that contains the JavaScript driver. These repos can also be found on NPM under their respective Node modules names.

* [Ambient (Light & Sound) Module](https://github.com/tessel/ambient-attx4)
* [RFID/NFC Module](https://github.com/tessel/rfid-pn532)
* [Accelerometer Module](https://github.com/tessel/accel-attx4)
* [Bluetooth Low Energy Module](https://github.com/tessel/ble-ble113a)
* [Climate (temperature & humidity) Module](https://github.com/tessel/climate-si7020)
* [GPS Module](https://github.com/tessel/gps-a2235h)
* [Infrared Module](https://github.com/tessel/ir-attx4)
* [Relay Module](https://github.com/tessel/relay-mono)
* [Servo Module](https://github.com/tessel/servo-pca9685)

##### USB Modules
USB Modules haven't been released yet so some don't have Github repos and many are in progress. In general, Tessel supports the following kind of USB modules which you can find from many online vendors:
* [Bluetooth Low Energy Dongles](https://github.com/sandeepmistry/noble)
* Cellular (3G/4G) Dongles (no Github module, it just works through the Node `http` module and similar for other languages)
* [Audio Recording/Playback](https://github.com/tessel/node-audiovideo)
* [Video Cameras (specifically, webcams)](https://github.com/tessel/node-audiovideo)
* Flash Storage Devices (no Github module, it just works through the Node `fs` module and similar for other languages)


## System Architecture

### High Level Look At Hardware
Below is a high level diagram of the hardware architecture:
![T2 Hardware Diagram](https://docs.google.com/drawings/d/124Qrry4MCywzKJq1mQSo8Xwk_S58YT4IG4OHf_2oUWM/pub?w=960&h=720)

As you can see from the diagram, the Atmel co-processor manages the USB connection and can communicate with the MediaTek through a SPI bus. The MediaTek can execute user scripts, and when it interprets hardware commands (like pulling a GPIO high or sending data over I2C), it packages it up and sends it over to the Atmel over a pre-defined protocol on that SPI bus. 

### Software Architecture
The MediaTek is responsible for managing the two USB Host ports, the ethernet port, and the WiFi network interace directly from the OpenWRT Operating System.

Let's take a look at the software architecture of Tessel 2:
![T2 Software Architecture Diagram](https://docs.google.com/drawings/d/1PHXdbOQEIMa7lVsBzazaMPgGdrh_LRcIpF4FlbPXmxo/pub?w=782&h=1097)


The USB Port on the Atmel actually has three interfaces to the to the MediaTek:
1. A UART connection that acts a serial terminal to the MediaTek. You can use a program like [`dterm`](http://decimus.net/dterm) to access the console through this connection.
2. A direct connection to the SPI Flash bus of the MediaTek. This allows the Atmel to rewrite the OpenWRT image and helps prevent the Tessel from becoming bricked by any corruptions to OS.
3. A SPI bus connection to the MediaTek for arbitrary data.

## A Code Deploy Example
A good method of understanding all the components of the system is to go through an example of running a simple script on Tessel 2:

#### The user code to light up an LED
The user might have code like the example below to light up LED 0 on Tessel 2.
```.js 
var tessel = require('tessel');
tessel.led[0].high();
```
#### Deploy with the CLI
First, the user will use the [command line interface](https://www.github.com/tessel/t2-cli) to deploy the script from the host computer:
```
t2 run index.js
```
The CLI will compress the code and break this simple `run` command into a [number of bash commands](https://github.com/tessel/t2-cli/blob/master/lib/tessel/commands.js) required to deploy the code like [untarring the code](https://github.com/tessel/t2-cli/blob/90bb45d4c82f019f6de97306a6fecf15e64d0a04/lib/tessel/commands.js#L17) and [running it with Node](https://github.com/tessel/t2-cli/blob/90bb45d4c82f019f6de97306a6fecf15e64d0a04/lib/tessel/commands.js#L20).

#### Accepting USB Communication On The Atmel
The utf-8 encoding of each command is sent over the USB connection via a [USB pipe](https://github.com/tessel/t2-firmware/blob/85c37ea67c9a85cf4f2d87aa8c27c7e0f41c4ffc/firmware/usbpipe.c). The USB pipe driver hands off the data to the general purpose [SPI bridge](https://github.com/tessel/t2-firmware/blob/85c37ea67c9a85cf4f2d87aa8c27c7e0f41c4ffc/firmware/bridge.c) (labeled as "SPI SLAVE SERCOMMx" in the diagram above) which transfers the command to the MediaTek. 

#### Relaying Data to the MediaTek SPI Daemon
On the MediaTek, the [SPI Daemon](https://github.com/tessel/t2-firmware/blob/85c37ea67c9a85cf4f2d87aa8c27c7e0f41c4ffc/soc/spid.c) is constantly waiting for data over the SPI bus and checks whether this data is from one of the module ports (for example, if an analog voltage was previously requested and was now returning the result) or from the USB port. 

The [shell script](https://github.com/tessel/t2-firmware/blob/85c37ea67c9a85cf4f2d87aa8c27c7e0f41c4ffc/soc/spid.sh) that starts up the SPI Daemon on boot also creates three unix domain sockets: one for Module Port A (`/var/run/tessel/port_a`), one for Module Port B  (`/var/run/tessel/port_b`), and one for USB  (`/var/run/tessel/usb`). We'll get to the two module ports in a moment, but first, the data from the CLI is passed into the USB domain socket.

#### One More Relay Into The USB Daemon
Waiting on the other end of the domain socket is [the USB Daemon](https://github.com/tessel/t2-firmware/blob/85c37ea67c9a85cf4f2d87aa8c27c7e0f41c4ffc/soc/usbexecd.c). This program has the thrilling task of accepting shell commands, initializing new threads to execute them, and routing stdin, stdout, and stderr of those threads back to the CLI. 

So by this point, the CLI has executed [a handful of bash commands](https://github.com/tessel/t2-cli/blob/90bb45d4c82f019f6de97306a6fecf15e64d0a04/lib/tessel/deploy.js#L24-L48) that transferred the code onto the Tessel 2 and started a Node process to run it. The next question is how we actually do anything with the hardware.

#### Accessing Hardware Through `tessel.js`
For JavaScript files, the answer comes from the ``` var tessel = require('tessel')``` line of the user script. When Node executes this on the MediaTek, it finds the [`tessel` module](https://github.com/tessel/t2-firmware/blob/85c37ea67c9a85cf4f2d87aa8c27c7e0f41c4ffc/node/tessel.js) in `/usr/lib/node/tessel.js`. When this file is executed, [it connects to a domain socket for each module port](https://github.com/tessel/t2-firmware/blob/85c37ea67c9a85cf4f2d87aa8c27c7e0f41c4ffc/node/tessel.js#L12-L15): two of the three domain sockets created by the SPI Daemon earlier! That means that whenever you run a command on a port like `tessel.led[0].high()`, it's [packaging that command into a array of bytes](https://github.com/tessel/t2-firmware/blob/85c37ea67c9a85cf4f2d87aa8c27c7e0f41c4ffc/node/tessel.js#L298) and sending it back over the SPI bus to the Atmel bridge firmware! That firmware then parses the command as pulling the specific GPIO high, and executes it. It can then return the result of that operation back through the SPI bus to the MediaTek SPI Daemon. 

#### Why Domain Sockets?
The beauty of this architecture with domain sockets is that most legitimate programming langauges have the capability to utilize domain sockets. This is how Tessel 2 can be used by any language, not just JavaScript (the code that packages up the commands into array byes just has to be ported to that language first). 

#### How Does Deploying Code over LAN Work Into This?
In the case of a LAN connection over WiFi or Ethernet, the procedure is much the same except all of the shell commands are executed over SSH. All of the module port communication between the SPI Daemon and the USB Bridge firmware is entirely the same. That's why the CLI is able to abstract out USB and LAN interfaces [into a single `Connection` object](https://github.com/tessel/t2-cli/blob/90bb45d4c82f019f6de97306a6fecf15e64d0a04/lib/tessel/tessel.js#L7) that simply accepts shell commands and returns a process object with the three streams (stdin, stdout, stderr) regardless of physical connection.

#### What is UCI/ubus on the diagram above?
[UCI](http://wiki.openwrt.org/doc/uci/system) and [ubus](http://wiki.openwrt.org/doc/techref/ubus) are unique features of OpenWRT that essentially let you access system configuration programmatically and receive results in a JSON format. It's very handy for the command line interface. You can see that the CLI makes [use of these features](https://github.com/tessel/t2-cli/blob/90bb45d4c82f019f6de97306a6fecf15e64d0a04/lib/tessel/commands.js#L35) heavily, especially for wifi related settings.

## Questions?

Ask us on [Slack](tessel.slack.com) (join [here](http://tessel-slack.herokuapp.com/) if you haven't already) or ask on [the forums](https://forums.tessel.io).

## More Useful Links
- [Current CLI Development Roadmap](https://github.com/tessel/t2-cli#development-milestones)
- [OpenWRT website](https://openwrt.org/)
- [MediaTek MT7620 datasheet](http://www.anz.ru/files/mediatek/MT7620_Datasheet.pdf)
- [Atmel SAMD21 datasheet](http://www.atmel.com/images/atmel-42181-sam-d21_datasheet.pdf)
- [Tessel Project Blog](https://tessel.io/blog)
- [Getting Started with Node](https://nodejs.org/documentation/tutorials/)
