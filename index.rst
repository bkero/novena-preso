
.. Novena: The Hacker's Laptop slides file, created by
   hieroglyph-quickstart on Thu Apr 21 22:23:21 2016.

===========================
Novena: The Hacker's Laptop
===========================

Ben Kero

About
=====

Me

Me
--
* Redhat engineer
* OpenStack
* Hobby is embedded Linux

History
-------

* TODO: Pic of Indiegogo page
* Guys behind it: "Bunnie" Huang and Sean "Xobs" Cross


Origins of the project
----------------------

* Creator always wanted to build a laptop just as it was possible to build a desktop
* Sick of laptops not having the capabilities to accomplish the day-to-day tasks of a hardware hacker
* Found a friend/cofounder to work on the project with him


Normal laptops
--------------

* Have less and less ports over time
* More closed platforms over time (even Intel with firmware blobs)
* No laptops have FPGAs, SDRs, UARTS, JTAG, or dual ethernet


Vision of the Novena
--------------------

* Everything a hardware hacker could want.
* FPGA, SDR, UARTs, JTAG, dual ethernet for sniffing
* Breakout board with digital/analog I/O ports, 3.3V/5V rails
* Extra room inside for everything else you need (tools, etc)
* Well-supported blob-free wifi
* A device that would be comfortable to use every day
* Interesting form factor


Result of the constructed hardware
----------------------------------

* Delivered on everything that was promised
* Screen quality is great
* Platform is delicate
* Works out of the box
* Linux support is good, but is missing the polish of Intel drivers


GPS
---

* Used GNSS-SDR to create a GPS device for the system to use (GNOME Maps)
* Also spoof GPS data: gps-sdr-sim project

FM Receiver
-----------

* FM receiver to listen to music
* Fast enough to listen to multiple stations at once

Fun with Cell Phones
--------------------

* Ran GSM base station (with data!) with OpenBTS, made phone calls
* Can handle multiple handsets
* 900MHz = unlicensed!


DIY processors and stupid FPGA tricks
-------------------------------------

* Learned FPGAs with the Xilinx
* Mined bitcoin with the FPGA, later litecoin


My projects
-----------

* Transplanting into ThinkPad case
* Universal battery interface


Projects influenced/spun out
----------------------------

* Librem 13 (that has its own problems)
* LVDS -> eDP adapter is used for a lot of retrofit hardware
* Senoko battery device


Current status of the project
-----------------------------

* Apt repos haven't been updated since Sep 15
* Xobs rebased the kernel for 4.4, up to r7
* xf86-video-armada + etnaviv projcets continue (etnaviv last updated jan19)
* Makers continue to use it (Ben Heck show made new case)


Community
---------

* Forums (kosagi.com/forums)
* IRC (#kosagi, irc.oftc.net)

Ways that the project lives on
------------------------------
* Senoko battery board
* Model for hardware development: Wiki, github
* Model for software release: Wiki, github
* Provided QA testing bits
* LVDS -> eDP adapter used in a lot of other projects (and standalone) now
* For instance, enterprising hackers are using it to retrofit HD panels into old ThinkPads
