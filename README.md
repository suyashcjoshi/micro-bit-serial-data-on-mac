

## How to read Serial Data from micro:bit on your Mac OS

### 1. Print to the console data that you want to read via serial connection

Sample code below prints accelerometer data from both x and y axis continuously, feel free to modify as per your needs.

```
basic.forever(function () {
    serial.writeLine("" + (input.acceleration(Dimension.X)))
    serial.writeLine("" + (input.acceleration(Dimension.Y)))
})
```

### 2. Read the data from device using 'screen' tool from Mac Terminal

- Make sure micro:bit is plugged it and program above is running
- Open a new terminal application. 
- Type `ls /dev/cu.*` to get a list of connected serial devices; one of them will look like `/dev/cu.usbmodem1422` (the exact number depends on your device).
- Type `screen /dev/cu.usbmodem1422 115200`, replacing the 'usbmodem information' with the one you found in the previous step. 115200 bits/sec is standard baud rate at which it will show data. This will open the micro:bit's serial output and show all messages received from the device. 
- To exit screen utility, press *Ctrl-A then Ctrl-D*

**Reference for more information**

micro:bit help guide: https://support.microbit.org/support/solutions/articles/19000022103-outputing-serial-data-from-the-micro-bit-to-a-computer
