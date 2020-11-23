# **NVIDIA Reflex Latency Analyzer Mice Database**

NVIDIA Reflex Latency Analyzer is a revolutionary system latency
measurement device designed to help gamers measure the responsiveness of
their PC. By detecting clicks coming from your mouse and measuring the
time it takes for the resulting pixels to change on screen, NVIDIA
Reflex Latency Analyzer can instantly break down the latency in your
system.

Mouse latency is a critical part of the system latency equation: Mouse
Latency + PC Latency + Display Latency = System Latency. The database in
this repository contains the set of tested mice that NVIDIA has
validated; containing both Reflex Latency Analyzer compatible mice, and
popular non-compatible mice.

This database is used by the Reflex Latency Analyzer to identify mice
and provide a database average when the mouse does not support per-click
latencies.

## **Contents**

This repository contains an Excel Workbook consisting of popular Esports
mice, mice attributes, and left mouse button click latency.

## **Components**

### Mouse DB tab

   | **Column**| **Description** | **Example** |
   |------------|-----------------|------------|
   |**make**| Brand |Logitech G|
   |**model**| Product |PRO X SUPERLIGHT (wired)|
   |**vid**| Vendor ID |046d|
   |**pid**| Product ID |c094|
   |**revision**| Firmware version tested (BCD Device ID)|2500|
   |**mode**| `<wired / wireless>`<br>- Whether the mouse is operating wired or wirelessly|wired|
   |**type**| `<wired / wireless / none>`<br>- Reported through the USB Extension<br>- Implemented by the mouse manufacturer<br>- This field can be "none" if the vendor is not using our extension |none|
   |**reportExtensionId**| `<TRUE / FALSE>`<br>- If the mouse reports PID, VID, and Revision extension<br>- This is used by the mouse vendor to indicate a different PID and Revision in cases where the device |FALSE|
   |**perClickLatency**| `<TRUE / FALSE>`<br>- If the mouse firmware implements per click latency |TRUE|
   |**polledActuation**| `<TRUE / FALSE>`<br>- If the mouse uses polled actuation<br>- An example of this is an optical switch that pulses the detection laser |FALSE|
   |**pulseFrequencyHz**| Zero unless the mouse uses polledActuation<br>- How often the mouse checks to see if there was a click<br>- This measurement can only be taken with an oscilloscope |0|
   |**actuationDetectionDurationHz**| The amount of time the mouse will accept a click per cycle<br>- For optical mice, this is the amount of time the detection light / laser is on |0|
   |**maximumHosePollRateHz**| Maximum polling rate supported by the mouse |1000|
   |**avgLmbLatencyUs**| Average latency of 500 clicks |808|
   |**stdDevUs**| Standard deviation of 500 clicks |302|
   |**adjustedAvgLmbLatencyUs**| ((1000 \* (pulseFrequency / maximumHostPollRate) - actuationDetectionDuration) / 2) + avgLMBLatency |808|
   |**TestedBy**| Who tested the mouse<br>- NVIDIA only for now |NVIDIA|

### Mouse brand workbook tabs

*  Mice brands that have three or more tested mice should have their own worksheet tab.

*  Each column represents mouse make, model, minimum, maximum, average, standard devviation, and 500 recorded left mouse button click latencies.

## **Licensing**

By contributing to this document the contributor acknowledges that that
all contributions are licensed under [CC BY4.0](https://creativecommons.org/licenses/by/4.0/).

## **Additional Information**

[**NVIDIA Reflex**](https://www.nvidia.com/en-us/geforce/news/reflex-low-latency-platform/)

[**Mouse Partner** ](https://developer.nvidia.com/reflex-mice-partner-program-interest)
