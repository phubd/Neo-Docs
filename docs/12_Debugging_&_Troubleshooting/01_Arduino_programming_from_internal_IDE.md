Please do not download the Arduino IDE from the Arduino website. Follow [this guide](!Getting_Started/Use_as_an_Arduino) instead.

## flash: uploading input firmware failed
If you get this error while the IDE is uploading the sketch from internal IDE:

``` bash
/usr/bin/udooneo-m4uploader: line 86: 11091 Bus
error              $up "$INPUT" 2>&1
flash: uploading input firmware failed
```

Type this command in a terminal and reboot the board.

``` bash
rm /var/opt/m4/m4last.fw
sudo reboot
```


##
If you get this error while the IDE is uploading the sketch:

``` bash
processing.app.debug.RunnerException
at cc.arduino.packages.uploaders.SerialUploader.uploadUsingPreferences(SerialUploader.java:131)
at processing.app.debug.Compiler.upload(Compiler.java:165)
at processing.app.Sketch.upload(Sketch.java:1167)
at processing.app.Sketch.exportApplet(Sketch.java:1141)
at processing.app.Sketch.exportApplet(Sketch.java:1113)
at processing.app.Editor$DefaultExportHandler.run(Editor.java:2377)
at java.lang.Thread.run(Thread.java:745)
Caused by: processing.app.SerialException: Error touching serial port '/dev/ttyMCC'.
at processing.app.Serial.touchForCDCReset(Serial.java:92)
at cc.arduino.packages.uploaders.SerialUploader.uploadUsingPreferences(SerialUploader.java:120)
... 6 more
Caused by: jssc.SerialPortException: Port name - /dev/ttyMCC; Method name - openPort(); Exception type - Port busy.
at jssc.SerialPort.openPort(SerialPort.java:162)
at processing.app.Serial.touchForCDCReset(Serial.java:86)
... 7 more
```

or

``` bash
... Bus Error.
```

For the moment it's necessary to reboot the board.
