<h1><img src="http://enroute.osgi.org/img/enroute-logo-64.png" witdh=40px style="float:left;margin: 0 1em 1em 0;width:40px">
IoT LED application</h1>

This repository is a typical Internet of Things (IoT) application based on [OSGi][1] framework. The application is developed in the [Eclipse][2] environment with [Bndtools][3] templates following [OSGi enRoute][4] tutorials. The workspace has support for [continuous integration][5] with [gradle][6].

The application is based on [OSGi enRoute IoT tutorial][7]. Its purpose is to control a hardware with the help of a [Raspbery Pi][8]. In this tutorial a LED is turned on and off based on an event triggered by a physical push-button and a programmed schedule.

The chip [BCM2835][9] controls and gets input from hardware. The pins of this chip are assigned and registered with the [Pi4J GpioController][11]. The bundle [OSGi enRoute][12] bundle *osgi.enroute.iot.pi.provider* (a version of the [Pi4j][10] library) is employed for this purpose.

##Prerequisites

The following software is needed:
* [Java 8][12]
* [Eclipse Mars][13]
* [Git][14]
* [Bndtools][15] version 3.1.0 or later.

The necessary hardware consist of:

* Raspberry Pi 2 model B setup with [NOOBS][16]
* LEDs 
* resistors \pm 220\Omega 
* breadboard
* push-buttons
* male-female wires

##Service structure

The purpose of the *LedApplication* class is to be an interface of the underlying services. It is not recommended to provide functionality to such interfaces. 

*OSGi enRoute* has a special templates for various projects types:

* Application projects *.application*, bind together a set of components and parametrizes them
* API projects *.api*, defines the service
* Provider projects *.provider*, *.adapter*, implements a project
* Test Projects *.test*, runs tests inside the framework


##References

[1]:  http://osgi.org/
[2]:  https://eclipse.org/
[3]:  http://bndtools.org/
[4]:  http://enroute.osgi.org/book/150-tutorials.html
[5]:  http://enroute.osgi.org/tutorial_base/800-ci.html
[6]:  https://www.gradle.org/
[7]:  http://enroute.osgi.org/tutorial_iot/050-start.html
[8]:  https://www.raspberrypi.org/products/raspberry-pi-2-model-b/
[9]:  https://www.raspberrypi.org/documentation/hardware/raspberrypi/bcm2835/README.md
[10]: http://pi4j.com
[11]: http://pi4j.com/example/control.html
[12]: http://www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html
[13]: https://www.eclipse.org/downloads/
[14]: https://git-scm.com/book/en/v2/Getting-Started-Installing-Git
[15]: http://bndtools.org/installation.html#update-site
[16]: https://www.raspberrypi.org/blog/new-raspbian-and-noobs-releases/