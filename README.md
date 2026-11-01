# RadiaNano — Android + Arduino Nano USB serial monitor

This is an Android Studio project, not a prebuilt APK. Open the folder in Android Studio and build/run it on an Android phone with USB host/OTG.

## Arduino serial protocol
Set Arduino baud rate to **9600** and send one line per update:
```cpp
Serial.println("CPM:12");
Serial.println("PULSE:345");
```
Accepted lines:
- `CPM:42` (or `CPM=42`, or just `42`) updates the CPM display and chart.
- `PULSE:123` / `COUNT:123` / `TOTAL:123` updates total pulse count.

Example test sketch (this is only a serial protocol test; it does not read a photodiode):
```cpp
void setup() {
  Serial.begin(9600);
}
void loop() {
  Serial.println("CPM:0");
  Serial.println("PULSE:0");
  delay(1000);
}
```

## Hardware notes
- Use a USB data cable and USB-C OTG adapter. Phone must support USB host/OTG.
- Works with common USB-serial chipsets supported by usb-serial-for-android (e.g. CH340/CP210x/FTDI, depending on adapter/driver).
- This app reads serial text; it does not implement the proprietary RadiaCode protocol.
- The displayed CPM is only what the Arduino sends. It is not automatically a calibrated radiation dose.
- Do not show µSv/h until you calibrate the complete detector against a suitable reference instrument/source and establish a detector-specific conversion factor.
- The app defaults to 9600 baud, 8-N-1.
