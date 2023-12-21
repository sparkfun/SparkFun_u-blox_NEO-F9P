SparkFun GNSS-RTK L1/L5 Breakout - NEO-F9P (Qwiic)
========================================

[![SparkFun GNSS-RTK L1/L5 Breakout - NEO-F9P (Qwiic)](https://cdn.sparkfun.com/r/600-600/assets/parts/2/3/4/8/5/GPS-23288-L1-L5-Breakout-NEO-F9P-Feature.jpg)](https://www.sparkfun.com/products/23288)

[*SparkFun GNSS-RTK L1/L5 Breakout - NEO-F9P (Qwiic) (GPS-23288)*](https://www.sparkfun.com/products/23288)

The SparkFun GNSS-RTK L1/L5 Breakout - NEO-F9P (Qwiic) is a high-precision GNSS board with equally impressive configuration options. The NEO-F9P is an upgrade to the NEO-M8P and utilizes the L1/L5 bands instead of the L1/L2 bands. Utilizing the L5 band, the NEO-F9P delivers improved performance under challenging urban environments because the L5 signals fall within the protected ARNS (aeronautical radio navigation service) frequency band. This band is less subject to RF interference.

The NEO-F9P module is a powerful 184-channel u-blox F9 engine GNSS receiver, meaning it can receive signals from the GPS, GLONASS, Galileo, and BeiDou constellations with 10mm, three-dimensional accuracy! That's right; such accuracy can be achieved with an RTK navigation solution when used with a correction source. With this board, you will be able to know where your (or any object's) X, Y, and Z location is within roughly the width of your fingernail! The module supports the concurrent reception of four GNSS systems. This module features a survey-in mode, allowing the module to become a base station and produce RTCM 3.x correction data.

We've included a rechargeable backup battery to keep the latest module configuration and satellite data available for up to two weeks. This battery helps 'warm-start' the module, decreasing the time-to-first-fix dramatically from a cold start of ~27s down to a hot start of ~3s. The battery will maintain RTC and GNSS orbit data without being connected to power for plenty of time. We have included an SMA connector for a secure connection.

The GNSS-RTK even has five communications ports, which are all active simultaneously: USB-C (which enumerates as a COM port), UART1 (with 3.3V TTL), UART2 for RTCM reception (with 3.3V TTL), I<sup>2</sup>C, and SPI. Utilizing our handy Qwiic system, no soldering is required to connect it to the rest of your system. However, we still have broken out 0.1"-spaced pins if you prefer a breadboard.

u-blox-based GPS products are configurable using the popular but dense Windows program u-center. Many different functions can be configured on the NEO-F9P: baud rates, update rates, geofencing, spoofing detection, external interrupts, SBAS/D-GNSS, increasing the high precision RTK solution to 20Hz, etc. All of this can be done within the SparkFun Arduino Library!

Our extensive [Arduino Library for u-blox modules](https://github.com/sparkfun/SparkFun_u-blox_GNSS_v3) makes reading and controlling the GNSS-RTK over our [Qwiic Connect System](https://www.sparkfun.com/qwiic) easy. Leave NMEA behind! Start using a much lighter-weight binary interface and give your microcontroller a break. The SparkFun Arduino library shows how to read latitude, longitude, even heading, and speed over I<sup>2</sup>C without constant serial polling.

Repository Contents
-------------------

* **/Hardware** - Eagle design files (.brd, .sch)

Documentation
--------------

* [**Installing an Arduino Library Guide**](https://learn.sparkfun.com/tutorials/installing-an-arduino-library) - Basic information on how to install an Arduino library.
* **[Library](https://github.com/sparkfun/SparkFun_u-blox_GNSS_Arduino_Library)** - Arduino library for the NEO-F9P.
* **[Hookup Guide](http://docs.sparkfun.com/SparkFun_u-blox_NEO-F9P/)** - Basic hookup guide for the NEO-F9P breakout board.

Product Versions
----------------

* [GPS-23288](https://www.sparkfun.com/products/23288) - Initial release

Version History
---------------
* v1.1 - Initial release

License Information
-------------------

This product is _**open source**_!

Please review the LICENSE.md file for license information.

If you have any questions or concerns on licensing, please contact technical support on our [SparkFun forums](https://forum.sparkfun.com/viewforum.php?f=152).

Distributed as-is; no warranty is given.

- Your friends at SparkFun.

_<COLLABORATION CREDIT>_
