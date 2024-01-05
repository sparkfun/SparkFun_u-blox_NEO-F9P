The [SparkFun GNSS-RTK L1/L5 Breakout - NEO-F9P (Qwiic)](https://www.sparkfun.com/products/23288) is a high precision GNSS board with equally impressive configuration options. Utilizing both the L1 and L5 bands, the NEO-F9P delivers improved performance under challenging urban environments because the L5 signals fall within the protected ARNS (aeronautical radionavigation service) frequency band. This band is less subject to RF interference.

<center>
<div class="grid cards" style="width:500px;" markdown>

-   <a href="https://www.sparkfun.com/products/23288">
      <figure markdown>
        <img src="https://cdn.sparkfun.com/assets/parts/2/3/4/8/5/GPS-23288-L1-L5-Breakout-NEO-F9P-Feature.jpg" style="width:140px; height:140px; object-fit:contain;" alt="SparkFun GNSS-RTK L1/L5 Breakout - NEO-F9P (Qwiic)">
      </figure>
    </a>

    ---

    <a href="https://www.sparkfun.com/products/23288">
      <b>SparkFun GNSS-RTK L1/L5 Breakout - NEO-F9P (Qwiic)</b>
      <br />
      GPS-23288
      <br />
      <center>[Purchase from SparkFun :fontawesome-solid-cart-plus:](https://www.sparkfun.com/products/23288){ .md-button .md-button--primary }</center>
    </a>

</div>
</center>

Similar to the ZED-F9P, the NEO-F9P module is a 184-channel u-blox F9 engine GNSS receiver, meaning it can receive signals from the GPS, GLONASS, Galileo, and BeiDou constellations with 10mm, three-dimensional accuracy! That's right; such accuracy can be achieved with an RTK navigation solution when used with a correction source. With this board, you will be able to know where your (or any object's) X, Y, and Z location is within roughly the width of your fingernail! Of course, the requirements for high precision GNSS requires a clear view of the sky (sorry, no indoor location) and a stream of correction data from an RTCM source. As long as you have two high precision breakout boards, or access to an online correction source, your NEO-F9P can output latitude, longitude, and altitude with centimeter grade accuracy. The module supports the concurrent reception of four GNSS systems. This module features a survey-in mode allowing the module to become a base station and produce RTCM 3.x correction data.

In this tutorial, we'll go over the hardware and how to hookup the breakout board. We will also go over a basic Arduino example to get started!



### Required Materials

To follow along with this tutorial, you will need the following materials. You may not need everything though depending on what you have. Add it to your cart, read through the guide, and adjust the cart as necessary.

* 1x [SparkFun IoT RedBoard - ESP32 Development Board [WRL-19177]](https://www.sparkfun.com/products/19177)
* 1x [Reversible USB A to C Cable - 0.8m [CAB-15425]](https://www.sparkfun.com/products/15425)
* 1x [SparkFun GNSS-RTK L1/L5 Breakout - NEO-F9P (Qwiic) [GPS-23288]](https://www.sparkfun.com/products/23288)
* 1x Qwiic Cable
    * [Flexible Qwiic Cable - 50mm [PRT-17260]](https://www.sparkfun.com/products/17260), for short distances
    * [Flexible Qwiic Cable - 500mm [PRT-17257]](https://www.sparkfun.com/products/17257), for those that need to wire the board farther away from your microcontroller
* 1x [Reinforced Interface Cable - SMA Male to TNC Male (10m) [CAB-21740]](https://www.sparkfun.com/products/21740)
* 1x [GNSS L1/L5 Multi-Band High Precision Antenna - 5m (SMA) [GPS-23814]](https://www.sparkfun.com/products/23814)


<div class="grid cards hide col-4" markdown>

<!-- ----------WHITE SPACE BETWEEN PRODUCTS---------- -->
-   <a href="https://www.sparkfun.com/products/19177">
      <figure markdown>
        <img src="https://cdn.sparkfun.com//assets/parts/1/8/8/0/0/ESP32_03.jpg" style="width:140px; height:140px; object-fit:contain;" alt="SparkFun IoT RedBoard - ESP32 Development Board">
      </figure>
    </a>

    ---

    <a href="https://www.sparkfun.com/products/19177">
      <b>SparkFun IoT RedBoard - ESP32 Development Board</b>
      <br />
      WRL-19177
    </a>
<!-- ----------WHITE SPACE BETWEEN PRODUCTS---------- -->
-   <a href="https://www.sparkfun.com/products/15425">
      <figure markdown>
        <img src="https://cdn.sparkfun.com//assets/parts/1/3/9/8/4/15425-Reversible_USB_A_to_C_Cable_-_0.8m-02.jpg" style="width:140px; height:140px; object-fit:contain;" alt="Reversible USB A to C Cable - 0.8m">
      </figure>
    </a>

    ---

    <a href="https://www.sparkfun.com/products/15425">
      <b>Reversible USB A to C Cable - 0.8m</b>
      <br />
      CAB-15425
    </a>
<!-- ----------WHITE SPACE BETWEEN PRODUCTS---------- -->
-   <a href="https://www.sparkfun.com/products/23288">
      <figure markdown>
        <img src="https://cdn.sparkfun.com/assets/parts/2/3/4/8/5/GPS-23288-L1-L5-Breakout-NEO-F9P-Feature.jpg" style="width:140px; height:140px; object-fit:contain;" alt="SparkFun GNSS-RTK L1/L5 Breakout - NEO-F9P (Qwiic)">
      </figure>
    </a>

    ---

    <a href="https://www.sparkfun.com/products/23288">
      <b>SparkFun GNSS-RTK L1/L5 Breakout - NEO-F9P (Qwiic)</b>
      <br />
      GPS-23288
    </a>
<!-- ----------WHITE SPACE BETWEEN PRODUCTS---------- -->
-   <a href="https://www.sparkfun.com/products/17260">
      <figure markdown>
        <img src="https://cdn.sparkfun.com//assets/parts/1/6/2/4/7/17260-Flexible_Qwiic_Cable_-_50mm-01.jpg" style="width:140px; height:140px; object-fit:contain;" alt="Flexible Qwiic Cable - 50mm">
      </figure>
    </a>

    ---

    <a href="https://www.sparkfun.com/products/17260">
      <b>Flexible Qwiic Cable - 50mm</b>
      <br>
      PRT-17260
    </a>
<!-- ----------WHITE SPACE BETWEEN PRODUCTS---------- -->
-   <a href="https://www.sparkfun.com/products/17519">
      <figure markdown>
        <img src="https://cdn.sparkfun.com//assets/parts/1/6/5/9/3/17519-GPS_Antenna_Ground_Plate-01.jpg" style="width:140px; height:140px; object-fit:contain;" alt="GPS Antenna Ground Plate">
      </figure>
    </a>

    ---

    <a href="https://www.sparkfun.com/products/17519">
      <b>GPS Antenna Ground Plate</b>
      <br>
      GPS-17519
    </a>
<!-- ----------WHITE SPACE BETWEEN PRODUCTS---------- -->
-   <a href="https://www.sparkfun.com/products/23814">
      <figure markdown>
        <img src="https://cdn.sparkfun.com//assets/parts/2/4/1/3/8/23814-L1-L5-Multi-Band-High-Precision-GNSS-Antenna-Feature.jpg" style="width:140px; height:140px; object-fit:contain;" alt="GPS Antenna Ground Plate">
      </figure>
    </a>

    ---

    <a href="https://www.sparkfun.com/products/23814">
      <b>GNSS L1/L5 Multi-Band High Precision Antenna - 5m (SMA)</b>
      <br>
      GPS-23814
    </a>
<!-- ----------WHITE SPACE BETWEEN PRODUCTS---------- -->
</div>



### GNSS Accessories &nbsp;_(Optional)_

Depending on your setup, you may need the following mounting hardware. As included earlier in the required materials, the antenna ground plate below is needed when using multi-band antennas that do not have a good ground plane.

* [GPS Antenna Ground Plate [GPS-17519]](https://www.sparkfun.com/products/17519)

<div class="grid cards hide col-4" markdown>

-   <a href="https://www.sparkfun.com/products/17519">
      <figure markdown>
        <img src="https://cdn.sparkfun.com//assets/parts/1/6/5/9/3/17519-GPS_Antenna_Ground_Plate-01.jpg" style="width:140px; height:140px; object-fit:contain;" alt="GPS Antenna Ground Plate">
      </figure>
    </a>

    ---

    <a href="https://www.sparkfun.com/products/17519">
      <b>GPS Antenna Ground Plate</b>
      <br />
      GPS-17519
    </a>
<!-- ----------WHITE SPACE BETWEEN PRODUCTS---------- -->
</div>



For users that decide to use the SPK6618H multi-band antenna as an alternative, users would not need to include the antenna ground plate. The mounting hardware listed below is also typically used with the SPK6618H multi-band antennas. The reinforced interface cable between the SMA to TNC also needed for the SPK6618H multi-band antennas.

* [GNSS Magnetic Mount [PRT-21257]](https://www.sparkfun.com/products/21257)
* [GNSS Antenna Mounting Hardware Kit [KIT-22197]](https://www.sparkfun.com/products/22197)
* [Reinforced Interface Cable - SMA Male to TNC Male (10m) [CAB-21740]](https://www.sparkfun.com/products/21740)
* [GNSS Multi-Band L1/L2/L5 Surveying Antenna - TNC (SPK6618H) [GPS-21801]](https://www.sparkfun.com/products/21801)

<div class="grid cards hide col-4" markdown>

-   <a href="https://www.sparkfun.com/products/21801">
      <figure markdown>
        <img src="https://cdn.sparkfun.com//assets/parts/2/1/5/9/7/SparkFun_GNSS_SPK6618H_Triband_Antenna_-_2.jpg" style="width:140px; height:140px; object-fit:contain;" alt="GNSS Multi-Band L1/L2/L5 Surveying Antenna - TNC (SPK6618H)">
      </figure>
    </a>

    ---

    <a href="https://www.sparkfun.com/products/21801">
      <b>GNSS Multi-Band L1/L2/L5 Surveying Antenna - TNC (SPK6618H)</b>
      <br />
      GPS-21801
    </a>
<!-- ----------WHITE SPACE BETWEEN PRODUCTS---------- -->
-   <a href="https://www.sparkfun.com/products/21257">
      <figure markdown>
        <img src="https://cdn.sparkfun.com//assets/parts/2/1/0/2/7/21257-_PRT_M90SD_Magnetic_Stand-_01.jpg" style="width:140px; height:140px; object-fit:contain;" alt="GNSS Magnetic Antenna Mount - 5/8" 11-TPI">
      </figure>
    </a>

    ---

    <a href="https://www.sparkfun.com/products/21257">
      <b>GNSS Magnetic Antenna Mount - 5/8" 11-TPI</b>
      <br />
      TOL-21257
    </a>
<!-- ----------WHITE SPACE BETWEEN PRODUCTS---------- -->
-   <a href="https://www.sparkfun.com/products/22197">
      <figure markdown>
        <img src="https://cdn.sparkfun.com//assets/parts/2/2/0/9/7/22197-_01.jpg" style="width:140px; height:140px; object-fit:contain;" alt="GNSS Antenna Mounting Hardware Kit">
      </figure>
    </a>

    ---

    <a href="https://www.sparkfun.com/products/22197">
      <b>GNSS Antenna Mounting Hardware Kit</b>
      <br />
      KIT-22197
    </a>
<!-- ----------WHITE SPACE BETWEEN PRODUCTS---------- -->
-   <a href="https://www.sparkfun.com/products/21740">
      <figure markdown>
        <img src="https://cdn.sparkfun.com//assets/parts/2/1/5/7/0/SparkFun_Reinforced_Interface_Cable_-_SMA_Male_to_TNC_Male_-_1.jpg" style="width:140px; height:140px; object-fit:contain;" alt="Reinforced Interface Cable - SMA Male to TNC Male (10m)">
      </figure>
    </a>

    ---

    <a href="https://www.sparkfun.com/products/21740">
      <b>Reinforced Interface Cable - SMA Male to TNC Male (10m)</b>
      <br />
      CAB-21740
    </a>
<!-- ----------WHITE SPACE BETWEEN PRODUCTS---------- -->


</div>



### Radios &nbsp;_(Optional)_

For users that require radios to transmit RTK correction data, you could use the following radios.

* [SiK Telemetry Radio V3 - 915MHz, 100mW [WRL-19032]](https://www.sparkfun.com/products/19032)
* [SparkFun LoRaSerial Kit - 915MHz (Enclosed) [WRL-20029]](https://www.sparkfun.com/products/20029)

<div class="grid cards hide col-4" markdown>

-   <a href="https://www.sparkfun.com/products/19032">
      <figure markdown>
        <img src="https://cdn.sparkfun.com//assets/parts/1/8/6/3/4/19032-SiK_Telemetry_Radio_V3_-_915MHz__100mW-01.jpg" style="width:140px; height:140px; object-fit:contain;" alt="SiK Telemetry Radio V3 - 915MHz, 100mW">
      </figure>
    </a>

    ---

    <a href="https://www.sparkfun.com/products/19032">
      <b>SiK Telemetry Radio V3 - 915MHz, 100mW</b>
      <br />
      WRL-19032
    </a>
<!-- ----------WHITE SPACE BETWEEN PRODUCTS---------- -->
-   <a href="https://www.sparkfun.com/products/20029">
      <figure markdown>
        <img src="https://cdn.sparkfun.com//assets/parts/1/9/7/9/0/SparkFun_LoRaSerial_Enclosed_-_20029-1.jpg" style="width:140px; height:140px; object-fit:contain;" alt="SparkFun LoRaSerial Kit - 915MHz (Enclosed)">
      </figure>
    </a>

    ---

    <a href="https://www.sparkfun.com/products/20029">
      <b>SparkFun LoRaSerial Kit - 915MHz (Enclosed)</b>
      <br />
      WRL-20029
    </a>
<!-- ----------WHITE SPACE BETWEEN PRODUCTS---------- -->

</div>



### Tools &nbsp;_(Optional)_

You will need a soldering iron, solder, and [general soldering accessories](https://www.sparkfun.com/categories/49) for a secure connection when using the plated through holes.

* [Soldering Iron [TOL-14456]](https://www.sparkfun.com/products/14456)
* [Solder Lead Free - 15-gram Tube [TOL-9163]](https://www.sparkfun.com/products/9163)
* [Flush Cutters - Xcelite [TOL-14782]](https://www.sparkfun.com/products/14782)
* [Hook-Up Wire - Assortment (Stranded, 22 AWG) [PRT-11375]](https://www.sparkfun.com/products/11375)
* [Wire Stripper - 20-30 AWG Solid (22-32 AWG Stranded) [TOL-22263]](https://www.sparkfun.com/products/22263)

<div class="grid cards hide col-4" markdown>

-   <a href="https://www.sparkfun.com/products/14456">
      <figure markdown>
        <img src="https://cdn.sparkfun.com//assets/parts/1/2/4/9/0/14456-01.jpg" style="width:140px; height:140px; object-fit:contain;" alt="Soldering Iron - 60W (Adjustable Temperature)">
      </figure>
    </a>

    ---

    <a href="https://www.sparkfun.com/products/14456">
      <b>Soldering Iron - 60W (Adjustable Temperature)</b>
      <br />
      TOL-14456
    </a>
<!-- ----------WHITE SPACE BETWEEN PRODUCTS---------- -->
-   <a href="https://www.sparkfun.com/products/9163">
      <figure markdown>
        <img src="https://cdn.sparkfun.com//assets/parts/2/5/8/7/09162-02-L.jpg" style="width:140px; height:140px; object-fit:contain;" alt="Solder Lead Free - 15-gram Tube">
      </figure>
    </a>

    ---

    <a href="https://www.sparkfun.com/products/9163">
      <b>Solder Lead Free - 15-gram Tube</b>
      <br>
      TOL-09163
    </a>
<!-- ----------WHITE SPACE BETWEEN PRODUCTS---------- -->
-   <a href="https://www.sparkfun.com/products/11375">
      <figure markdown>
        <img src="https://cdn.sparkfun.com//assets/parts/7/1/2/0/11375-Hook-Up_Wire_-_Assortment__Solid_Core__22_AWG_-01.jpg" style="width:140px; height:140px; object-fit:contain;" alt="Hook-Up Wire - Assortment (Stranded, 22 AWG)">
      </figure>
    </a>

    ---

    <a href="https://www.sparkfun.com/products/11375">
      <b>Hook-Up Wire - Assortment (Stranded, 22 AWG)</b>
      <br />
      PRT-11375
    </a>
<!-- ----------WHITE SPACE BETWEEN PRODUCTS---------- -->
-   <a href="https://www.sparkfun.com/products/22263">
      <figure markdown>
        <img src="https://cdn.sparkfun.com//assets/parts/2/2/2/0/1/22263-_TOL_Wire_Stripper-_01.jpg" style="width:140px; height:140px; object-fit:contain;" alt="Wire Stripper - 20-30 AWG Solid (22-32 AWG Stranded)">
      </figure>
    </a>

    ---

    <a href="https://www.sparkfun.com/products/22263">
      <b>Wire Stripper - 20-30 AWG Solid (22-32 AWG Stranded)</b>
      <br />
      TOL-22263
    </a>
<!-- ----------WHITE SPACE BETWEEN PRODUCTS---------- -->
-   <a href="https://www.sparkfun.com/products/14782">
      <figure markdown>
        <img src="https://cdn.sparkfun.com//assets/parts/1/3/0/3/6/14782-Flush_Cutters_-_Xcelite-02.jpg" style="width:140px; height:140px; object-fit:contain;" alt="Flush Cutters - Xcelite">
      </figure>
    </a>

    ---

    <a href="https://www.sparkfun.com/products/14782">
      <b>Flush Cutters - Xcelite</b>
      <br />
      TOL-14782
    </a>
<!-- ----------WHITE SPACE BETWEEN PRODUCTS---------- -->
</div>



### Prototyping Accessories &nbsp;_(Optional)_

For those using radios to connect a base station and rover together, you will need to connect to the PTHs. You could use IC hooks for a temporary connection depending on your setup and what you have available. Of course, you will want to the solder header pins for a secure connection. Below are a few prototyping accessories that you may want to consider.

* [Breadboard - Self-Adhesive (White) [PRT-12002]](https://www.sparkfun.com/products/12002)
* [IC Hook with Pigtail [CAB-09741]](https://www.sparkfun.com/products/9741)
* [Break Away Headers - Straight [PRT-00116]](https://www.sparkfun.com/products/116)
* [Female Headers [PRT-00115]](https://www.sparkfun.com/products/115)
* [Jumper Wires Premium 6" M/M Pack of 10 [PRT-08431]](https://www.sparkfun.com/products/8431)

<div class="grid cards hide col-4" markdown>
<!-- ----------WHITE SPACE BETWEEN PRODUCTS---------- -->
-   <a href="https://www.sparkfun.com/products/12002">
      <figure markdown>
        <img src="https://cdn.sparkfun.com/assets/parts/8/5/0/3/12002-Breadboard_-_Self-Adhesive__White_-01.jpg" style="width:140px; height:140px; object-fit:contain;" alt="Breadboard - Self-Adhesive (White)">
      </figure>
    </a>

    ---

    <a href="https://www.sparkfun.com/products/12002">
      <b>Breadboard - Self-Adhesive (White)</b>
      <br />
      PRT-12002
    </a>
<!-- ----------WHITE SPACE BETWEEN PRODUCTS---------- -->
-   <a href="https://www.sparkfun.com/products/9741">
      <figure markdown>
        <img src="https://cdn.sparkfun.com/assets/parts/3/6/9/6/09741-01.jpg" style="width:140px; height:140px; object-fit:contain;" alt="IC Hook with Pigtail">
      </figure>
    </a>

    ---

    <a href="https://www.sparkfun.com/products/9741">
      <b>IC Hook with Pigtail</b>
      <br>
      CAB-09741
    </a>
<!-- ----------WHITE SPACE BETWEEN PRODUCTS---------- -->
-   <a href="https://www.sparkfun.com/products/116">
      <figure markdown>
        <img src="https://cdn.sparkfun.com/assets/parts/1/0/6/00116-02-L.jpg" style="width:140px; height:140px; object-fit:contain;" alt="Break Away Headers - Straight">
      </figure>
    </a>

    ---

    <a href="https://www.sparkfun.com/products/116">
      <b>Break Away Headers - Straight</b>
      <br />
      PRT-00116
    </a>
<!-- ----------WHITE SPACE BETWEEN PRODUCTS---------- -->
-   <a href="https://www.sparkfun.com/products/115">
      <figure markdown>
        <img src="https://cdn.sparkfun.com/assets/parts/1/0/5/00115-03-L.jpg" style="width:140px; height:140px; object-fit:contain;" alt="Female Headers">
      </figure>
    </a>

    ---

    <a href="https://www.sparkfun.com/products/115">
      <b>Female Headers</b>
      <br />
      PRT-00115
    </a>
<!-- ----------WHITE SPACE BETWEEN PRODUCTS---------- -->
-   <a href="https://www.sparkfun.com/products/8431">
      <figure markdown>
        <img src="https://cdn.sparkfun.com/assets/parts/1/1/8/1/JumperWire-Male-01-L.jpg" style="width:140px; height:140px; object-fit:contain;" alt="Jumper Wires Premium 6" M/M Pack of 10">
      </figure>
    </a>

    ---

    <a href="https://www.sparkfun.com/products/8431">
      <b>Jumper Wires Premium 6" M/M Pack of 10</b>
      <br />
      PRT-08431
    </a>
<!-- ----------WHITE SPACE BETWEEN PRODUCTS---------- -->
</div>



### Suggested Reading

If you aren't familiar with the Qwiic Connection System, we recommend reading [here for an overview](https://www.sparkfun.com/qwiic).

<div style="text-align: center">
  <table style="border-style:none">
    <tr>
     <td style="text-align: center; vertical-align: middle;">
     <div style="text-align: center"><a href="https://www.sparkfun.com/qwiic"><img src="../assets/Qwiic-registered-updated.png" alt="Qwiic Connection System" title="Click to learn more about the Qwiic Connection System!"></a>
     </div>
    </td>
    </tr>
    <tr>
      <td style="text-align: center; vertical-align: middle;"><div style="text-align: center"><i><a href="https://www.sparkfun.com/qwiic">Qwiic Connection System</a></i></div></td>
    </tr>
  </table>
</div>

If you aren’t familiar with the following concepts, we also recommend checking out a few of these tutorials before continuing.

<div class="grid cards hide col-4" markdown>
<!-- ----------WHITE SPACE BETWEEN GRID CARDS---------- -->
-   <a href="https://learn.sparkfun.com/tutorials/9">
      <figure markdown>
        <img src="https://cdn.sparkfun.com/assets/parts/5/9/7/4/10890-01.jpg"style="width:264px; height:148px; object-fit:contain;" alt="GPS Basics">
      </figure>
    </a>

    ---

    <a href="https://learn.sparkfun.com/tutorials/9">
      <b>GPS Basics</b>
    </a>
<!-- ----------WHITE SPACE BETWEEN GRID CARDS---------- -->
-   <a href="https://learn.sparkfun.com/tutorials/i2c">
      <figure markdown>
        <img src="https://cdn.sparkfun.com/c/264-148/assets/learn_tutorials/8/2/I2C-Block-Diagram.jpg" style="width:264px; height:148px; object-fit:contain;" alt="I2C">
      </figure>
    </a>

    ---

    <a href="https://learn.sparkfun.com/tutorials/i2c">
      <b>I2C</b>
    </a>
<!-- ----------WHITE SPACE BETWEEN GRID CARDS---------- -->
-   <a href="https://learn.sparkfun.com/tutorials/iot-redboard-esp32-development-board-hookup-guide">
      <figure markdown>
        <img src="https://cdn.sparkfun.com/assets/learn_tutorials/2/2/5/7/285808434_548438690244031_7008413248633042033_n.jpg"style="width:264px; height:148px; object-fit:contain;" alt="IoT RedBoard ESP32 Development Board Hookup Guide">
      </figure>
    </a>

    ---

    <a href="https://learn.sparkfun.com/tutorials/iot-redboard-esp32-development-board-hookup-guide">
      <b>IoT RedBoard ESP32 Development Board Hookup Guide</b>
    </a>
<!-- ----------WHITE SPACE BETWEEN GRID CARDS---------- -->
-   <a href="https://learn.sparkfun.com/tutorials/installing-arduino-ide">
      <figure markdown>
        <img src="https://cdn.sparkfun.com/assets/learn_tutorials/6/1/arduinoThumb.jpg" style="width:264px; height:148px; object-fit:contain;" alt="Installing Arduino IDE">
      </figure>
    </a>

    ---

    <a href="https://learn.sparkfun.com/tutorials/installing-arduino-ide">
      <b>Installing Arduino IDE</b>
    </a>
<!-- ----------WHITE SPACE BETWEEN GRID CARDS---------- -->
-   <a href="https://learn.sparkfun.com/tutorials/installing-board-definitions-in-the-arduino-ide">
      <figure markdown>
        <img src="https://cdn.sparkfun.com/c/178-100/assets/learn_tutorials/1/2/6/5/sparkfun_boards.PNG" style="width:264px; height:148px; object-fit:contain;" alt="Installing Board Definitions in the Arduino IDE">
      </figure>
    </a>

    ---

    <a href="https://learn.sparkfun.com/tutorials/installing-board-definitions-in-the-arduino-ide">
      <b>Installing Board Definitions in the Arduino IDE</b>
    </a>
<!-- ----------WHITE SPACE BETWEEN GRID CARDS---------- -->
-   <a href="https://learn.sparkfun.com/tutorials/what-is-gps-rtk">
      <figure markdown>
        <img src="https://cdn.sparkfun.com/assets/learn_tutorials/8/1/3/Location-Wandering-GPS-combined.jpg" style="width:264px; height:148px; object-fit:contain;" alt="What is GPS RTK?">
      </figure>
    </a>

    ---

    <a href="https://learn.sparkfun.com/tutorials/what-is-gps-rtk">
      <b>What is GPS RTK?</b>
    </a>
<!-- ----------WHITE SPACE BETWEEN GRID CARDS---------- -->
-   <a href="https://learn.sparkfun.com/tutorials/getting-started-with-u-center-for-u-blox">
      <figure markdown>
        <img src="https://cdn.sparkfun.com/assets/learn_tutorials/8/1/5/u-center.jpg" style="width:264px; height:148px; object-fit:contain;" alt="Getting Started with U-Center for u-blox">
      </figure>
    </a>

    ---

    <a href="https://learn.sparkfun.com/tutorials/getting-started-with-u-center-for-u-blox">
      <b>Getting Started with U-Center for u-blox</b>
    </a>
<!-- ----------WHITE SPACE BETWEEN GRID CARDS---------- -->
-   <a href="https://learn.sparkfun.com/tutorials/serial-communication">
      <figure markdown>
        <img src="https://cdn.sparkfun.com/assets/7/d/f/9/9/50d24be7ce395f1f6c000000.jpg" style="width:264px; height:148px; object-fit:contain;" alt="Serial Communication">
      </figure>
    </a>

    ---

    <a href="https://learn.sparkfun.com/tutorials/serial-communication">
      <b>Serial Communication</b>
    </a>
<!-- ----------WHITE SPACE BETWEEN GRID CARDS---------- -->
-   <a href="https://learn.sparkfun.com/tutorials/how-to-solder-through-hole-soldering">
      <figure markdown>
        <img src="https://cdn.sparkfun.com/assets/learn_tutorials/5/Soldering_Action-01.jpg"style="width:264px; height:148px; object-fit:contain;" alt="How to Solder: Through-Hole Soldering">
      </figure>
    </a>

    ---

    <a href="https://learn.sparkfun.com/tutorials/how-to-solder-through-hole-soldering">
      <b>How to Solder: Through-Hole Soldering</b>
    </a>

    <!-- ----------WHITE SPACE BETWEEN GRID CARDS---------- -->
</div>

You may also be interested in the following blog posts on GNSS technologies.

<div class="grid cards col-4" markdown align="center">

-   <a href="https://www.sparkfun.com/news/4276">
	<figure markdown>
	![Tutorial Thumbnail](https://cdn.sparkfun.com/c/264-148/assets/home_page_posts/4/2/7/6/GPSvGNSSHomepageImage4.png)
	</figure>

	---

	**GPS vs GNSS**</a>

-   <a href="https://www.sparkfun.com/news/7138">
	<figure markdown>
	![Tutorial Thumbnail](https://cdn.sparkfun.com/c/264-148/assets/home_page_posts/7/1/3/8/SparkFun_RTK_Facet_-_Surveying_Monopod.jpg)
	</figure>

	---

	**What is Correction Data?**</a>

-   <a href="https://www.sparkfun.com/news/7533">
	<figure markdown>
	![Tutorial Thumbnail](https://cdn.sparkfun.com/c/264-148/assets/home_page_posts/7/5/3/3/rtk-blog-thumb.png)
	</figure>

	---

	**Real-Time Kinematics Explained**</a>

-   <a href="https://www.sparkfun.com/news/7401">
	<figure markdown>
	![Tutorial Thumbnail](https://cdn.sparkfun.com/c/264-148/assets/home_page_posts/7/4/0/1/Screen_Shot_2023-06-26_at_8.30.22_PM.png)
	</figure>

	---

	**New Video: Unlocking High-Precision RTK Positioning**</a>

</div>
