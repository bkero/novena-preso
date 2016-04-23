
.. Novena: The Hacker's Laptop slides file, created by
   hieroglyph-quickstart on Thu Apr 21 22:23:21 2016.

===========================
Novena: The Hacker's Laptop
===========================

Ben Kero

Novena: The Hacker's Laptop
===========================

What is Novena?
---------------

.. figure:: /_static/novena.jpg
   :align: center
   :scale: 50%

   http://crowdsupply.com/sutajio-kosagi/novena

* Open Source Laptop project
* Electrical engineering and security research focus
* Aimed at power users
* Usable components

.. note::
  * For those of you not sure if you're in the right place, let me jog your memory.
  * This talk is about the Novena, a fully open source laptop.
  * It's aimed at power users and has great attention to detail to include features that would be useful for performing security research or reverse engineering on hardware.

Me
--
* Day job is Linux
* Hobby is embedded Linux
* Novena backer, software contributor


Origins of the project
----------------------

.. figure:: /_static/bunnie.jpg
   :align: left
   :scale: 11%

   https://www.flickr.com/photos/kubina/934728529

.. figure:: /_static/xobs.jpg
   :align: right
   :scale: 30%

   ____________________________________________________________ http://www.bunniestudios.com/blog/?p=3554

* Creators: Andrew 'bunnie' Huang + Sean 'xobs' Cross
* Wanted a DIY laptop analogous to desktop
* It should do all the things that hardware hackers need it to do.
* Sick of laptops not having the capabilities to accomplish the day-to-day tasks of a hardware hacker

.. note::
    * These are the two creators. bunnie was previously known for writing the book on XBox reverse engineering and creating the Chumby project. Together with his cofounder xobs they founded Sutajio Ko-usagi (Kosagi). They're based out of Singapore and they make open hardware projects.
    * Creators always wanted to build a laptop, just as it's been possible to build desktops by selecting components.
    * It sucks to have to carry around all the hardware that you might need tof ra particular hardware hacking project.
    * 


.. slide::

  .. figure:: /_static/crowdsupply.png
     :align: center
     :class: fill


Normal laptops
--------------

* Have less and less ports over time
* More closed platforms over time (even Intel with firmware blobs)

.. figure:: /_static/macbook.jpg
   :align: center

   https://www.flickr.com/photos/pestoverde/17182400279

Vision of the Novena
--------------------

* Everything a hardware hacker could want.
* FPGA, SDR, UARTs, JTAG, dual ethernet for sniffing
* Breakout board with digital/analog I/O ports, 3.3V/5V rails
* Extra room inside for everything else you need (tools, etc)
* Well-supported blob-free wifi
* A device that would be comfortable to use every day
* Interesting form factor

.. note::
    * FPGA is a piece of hardware that allows you to design new microchips in software.
    * SDR is a software defined radio. This is so cool, it's almost like a magic wand to do weird things with radios like GPS, GSM communication, and so much more.
    * UARTs and JTAG are common protocols used in all sorts of hardware. Normal laptops need additional hardware to talk to these.
    * Dual ethernet is super handy for plugging unknown devices into the internet and sniffing their traffic. You'd be amazed how much crap that IoT devices spew.
    * Everything should be not only useable with open source and blob-free drivers, but have as much as possible good NDA-free docs for evelopment.
    * It should be a usable device for day-to-day tasks and settings

.. slide::

   .. figure:: /_static/novenaboard.jpg
      :class: fill
      :scale: 10%


Result of the constructed hardware
----------------------------------

* Delivered on everything that was promised
* Screen quality is great
* Platform is delicate
* Works out of the box
* Linux support is good, but is missing the polish of Intel drivers

.. note::
    * For what was the first time ever on any crowdfunded hardware project, they delivered everything that was promised, on a reasonable schedule. Chock one up to having experience in China and experience with hardware production. But I repeat myself.
    * The screen is an excellent 1080p IPS panel. It's crisp and sharp. Definitely top-tier laptop display.
    * Since it's mostly meant to live on a workbench it's a bit delicate. The gas strut in the display prop is cool, but it's a bit too delicate to throw in a backpack and mule around.
    * Everything works out of the box with Linux. This shouldn't be so surprising since it was designed to work with Linux in the first place. It comes with Debian jessie pre-installed.
    * Open video support is ongoing. We all knew it going in, but the graphics core has been notoriously closed-source. All mobile/arm graphics is a crapshoot, but these gc chips are shaping up to have the best open support. Compare to nouveau.

Software
--------

* Ships with Debian jessie
* Novena-specific packages in Novena repo
* Secure signing key
* All repositories come with package building scripts
* Firmware updates as packages
* Great wiki for docs (kosagi.com/w)
* Fantastic model for Linux-based hardware projects

.. note::
    * The Novena originally shipped with Debian jessie, still does
    * They use stock jessie repos, add one for novena-specific packages
    * This may seem simple, but they didn't screw it up!
    * They keep their signing key offline, on a machine that's never touched the internet

GPS
---

.. figure:: /_static/ingress.png
   :align: center
   :scale: 35%

* Used GNSS-SDR to create a GPS device for the system to use (GNOME Maps)
* Also spoof GPS data: gps-sdr-sim project

.. note::
    * Can be used as a simple GPS device in a completely free stack with OpenStreetMaps or GNOME maps or...
    * Can be a great BlackHat or prank tool with gps-sdr-sim. This allows the SDR to broadcast bogus GPS data, making the receivers think that you're somewhere else.
    * Has anybody here played Ingress? You know about walking around and finding portals and capturing? Yeah.

FM Radio 📻📻
-----------

.. figure:: /_static/fmradio.jpg
   :align: left
   :scale: 40%

   https://www.flickr.com/photos/51764518@N02/10525241293 CC-BY-SA 2.0

* FM receiver to listen to music
* Fast enough to listen to multiple stations at once
* Transmitty enough to host a (not) pirate radio station

.. note::
   * It can listen to radio stations. But then again so can your car.
   * It can listen to multiple radio stations at once! Cool if you're recording, but you can't hear both at once and remain sane.
   * It can also transmit.
   * I'd show you a pic of GNURadio, but screenshots of it are really complicated and boring. So I'm going to show you this picture of a cool old portable Fm radio instead.


Fun with Cell Phones 🍌
----------------------

.. figure:: /_static/bananaphone.jpg
   :align: right
   :scale: 20%

   https://commons.wikimedia.org/wiki/File:Banana_phone.jpg CC-BY-SA 2.0

* Ran GSM base station (with data!) with OpenBTS
* 📱📱 Phone calls 📱📱
* SMS
* Can handle multiple handsets
* 900MHz = amateur radio spectrum!


.. note::
   * Really cool in emergency preparedness situations. When infra goes out how will you communicate? How about in the woods?
   * 900MHz is 33cm band. Licensed as an amateur band. Be sure to check if this is legal before you do it.

DIY processors and stupid FPGA tricks
-------------------------------------

.. figure:: /_static/fpga.jpg
   :align: center
   :scale: 50%

   https://en.wikipedia.org/wiki/Xilinx#/media/File:Xilinx_Spartan-3E_%28XC3S500E%29.jpg CC-BY-2.0

* Learned FPGAs with the Xilinx
* Mine cryptocurrencies
* Interface with weird hardware!
* Real-time music visualizer

.. note::
    * FPGAs are really cool. They are basically used for writing custom computers in software that can be burned on to a chip and ran. This is how chip makers test their chips first. They're ran at a fraction of their normal speed in this FPGA as software, then they're laid out in hardware and manufactured. Afterwards they can crank the speed up.
    * Before manufacturing hardware to mine Bitcoin was a thing, FPGAs were used for the purpose and were orders of magnitude faster than desktop processors and GPUs. It's a fun exercise to write a miner.
    * You found a weird circuit board that's really hard to interface with? No problem. FPGAs are great for that sort of thing. You can model the entire interaction in software.
    * Finally, a last application is a real-time music visualizer. Since they're so fast and configurable, you can use them to do pretty math to make visualizations a la milkdrop or electricsheep.


Projects spun out: eDP board
----------------------------

.. figure:: /_static/edp.jpg
   :align: center
   :scale: 60%

   http://rightshift.info/starterkit/home/Project-Novena-X-part-3

* Older mobile computers use LVDS displays
* Adapter board converts embedded DisplayPort to LVDS
* Board design is open source
* Used to retrofit new LCDs in older PCs

.. note::
    * LVDS stands for... It's a transmission standard used on many (older) motherboards. Older motherboards have older displays, which usually means lower resolution.
    * People really love their machines, but want to upgrade them to support newer displays. Hence, an adapter is needed.


Projects spun out: Senoko Battery Board
---------------------------------------

.. figure:: /_static/senoko.jpg
   :align: center
   :scale: 25%

   http://bunniefoo.com/novena/pvt1_release/senoko_dvt1.jpg

* 18V input
* Uses hobby RC vehicle LiPo batteries

.. note::
    * These are the battery boards.
    * You can tell they did some clever things with ports.
    * It runs a little free realtime OS called ChibiOS
    * It comes with and runs on 3S lipo batteries, can be cheaply ordered from hobbyking.com
    * That white connector on top is the balance lead connector. It's used to automatically maintain the health of the battery.
    * Two of those 3-pin temperature headers are for temperature sensing. In the event the battery develops an internal short it will heat up. The sensor will pick it up and tell the board, which will then stop charging and throw an alarm.
    * Notice the 4 buttons on the right. If you're busy fooling with batteries these can be fun. They allow you to hot-reflash the firmware on the battery board.
    * The input voltage is 18V. This is conveniently close to the 20V used by a lot of laptops, including my favorites that may happen to rhyme with Pink Mad.
    * These boards are kind of rare, and currently the only way to get one is to hop onto the Novena forums and get one from a guy on there who does production runs of them. Super deep (dark?) web stuff.

Current status of the project
-----------------------------

* Repos last updated 3 weeks ago
* Xobs made beta repo for testing packages
* Relies on forked kernel: latest is 4.4
* xf86-video-armada + etnaviv projects continue (etnaviv last updated jan19)
* Makers continue to use it (Ben Heck show made new case)

.. note::
    * Xobs made beta repo about 3 weeks ago because the signing key was so hard to use.
    * The kernel is just barely forked. Hopefully the code can be upstreamed. Ther is still some effort going in to make the power management better.
    * Video driver updates are still ongoing. They're improving, but full-screen video can still be difficult.

Community
---------

* Independent blags
* Forums (kosagi.com/forums)
* IRC (#kosagi, irc.oftc.net)
* Join us!

Current community projects
--------------------------

.. figure:: /_static/benh-laptop.png
   :align: center
   :scale: 65%

   http://hackaday.com/2016/01/30/building-the-novena-laptop/

* Chassis making
* Alternative displays

.. note::
    * People are alternative cases made from things like books, aluminum bars with piano hinges, and 3d printed plastic cases
    * People are also experimenting with other displays such as Pixel Qi's tragically short-lived transflective displays and ePaper (industry-generic term for e-ink) displays


That's all
----------

Thanks for coming!

Questions?
