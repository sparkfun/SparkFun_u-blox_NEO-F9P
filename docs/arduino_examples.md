Now that we have our library and board add-on installed, we can get start experimenting with the breakout board. For the scope of this tutorial, we will highlight one of the examples to get started. From there we will be able to build our own custom code to integrate the development board into a project.



### Example 1: Positional Accuracy

As a quick test, we will be using the first example in the **ZED-F9P** folder (located in **File** **Examples** > **SparkFun u-blox GNSS V3** > **ZED-F9P** > **Example1_GetPositionAccuracy**).

If you have not already, select your Board (in this case the **SparkFun ESP32 IoT RedBoard**), and associated COM port. Upload the code to the board and set the [Arduino Serial Monitor](https://learn.sparkfun.com/tutorials/terminal-basics/all#arduino-serial-monitor-windows-mac-linux) to **115200** baud. Give the NEO-F9P a few minutes to get a satellite lock. The GPS coordinates and the accuracy will be output in the Serial Monitor.



### More Examples!

Now that you got it up and running, check out the other examples located in the ZED-F9P folder!

<div style="text-align: center"><a href="https://github.com/sparkfun/SparkFun_u-blox_GNSS_v3/tree/main/examples/ZED-F9P" target="github_gnss_v3" class="md-button">SparkFun_u-blox_GNSS_v3 > examples > ZED-F9P</a></div>

Of course, to get the most out of the NEO-F9P, you will need an RTCM correction source. Depending on your setup, you will probably need a second NEO-F9P for a correction source. The following project tutorials allow you to set up the ZED-F9P as a reference station or rover.

<div class="grid cards hide col-4" markdown>
<!-- ----------WHITE SPACE BETWEEN GRID CARDS---------- -->
-   <a href="https://learn.sparkfun.com/tutorials/1363">
      <figure markdown>
        <img src="https://cdn.sparkfun.com/assets/learn_tutorials/1/3/6/3/Roof_Enclosure.jpg" style="width:264px; height:148px; object-fit:contain;" alt="How to Build a DIY GNSS Reference Station">
      </figure>
    </a>

    ---

    <a href="https://learn.sparkfun.com/tutorials/1363">
      <b>How to Build a DIY GNSS Reference Station</b>
    </a>
<!-- ----------WHITE SPACE BETWEEN GRID CARDS---------- -->
-   <a href="https://learn.sparkfun.com/tutorials/1363">
      <figure markdown>
        <img src="https://cdn.sparkfun.com/assets/learn_tutorials/1/3/6/2/GNSS_RTK_DIY_Surveying_Tutorial.jpg" style="width:264px; height:148px; object-fit:contain;" alt="Setting up a Rover Base System">
      </figure>
    </a>

    ---

    <a href="https://learn.sparkfun.com/tutorials/1363">
      <b>Setting up a Rover Base System</b>
    </a>
<!-- ----------WHITE SPACE BETWEEN GRID CARDS---------- -->
