

## How to read Serial Data from micro:bit on your Mac OS

### 1. Write this code in JavaScript tab. Currently it's printing accelerometer data from both x and y axis continuously, feel free to modify as per your needs.

```
basic.forever(function () {
    serial.writeLine("" + (input.acceleration(Dimension.X)))
    serial.writeLine("" + (input.acceleration(Dimension.Y)))
})
```

### 2. Open the terminal app and connect to the micro:bit devie using screen

- Plug in the micro:bit and open a new terminal window. 
- Type ls `/dev/cu.*` to get a list of connected serial devices; one of them will look like `/dev/cu.usbmodem1422` (the exact number depends on your computer).
- Type screen `/dev/cu.usbmodem1422 115200`, replacing the 'usbmodem' number with the number you found in the previous step. 115200 bits/sec is the baud rate at which it will show data. This will open the micro:bit's serial output and show all messages received from the device. 
- To exit, press Ctrl-A then Ctrl-D.

**Reference for more information**

micro:bit help guide: https://support.microbit.org/support/solutions/articles/19000022103-outputing-serial-data-from-the-micro-bit-to-a-computer
