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

**Mouse DB tab**

1.  Make- brand
2.  Mode - product
3.  VID - vendor ID
4.  PID - product ID
5.  Revision - firmware version tested (BCD Device ID)
6.  Mode - wired / wireless
    * Whether the mouse is operating wired or wirelessly.
7.  Type - wired / wireless, reported through the USB Extension
    * Implemented by the mouse manufacturer
    * This field can be "none" if the vendor is not using our extension
8.  reportExtensionId - true if the mouse reports PID, VID, and Revision extension
    * This is used by the mouse vendor to indicate a different PID and Revision in cases where the device connected to the PC is a dongle or intermediate device.
9.  perClickLatency - true if the mouse firmware implements per click latency
10. polledActuation - true if the mouse uses polled actuation
    * An example of this is an optical switch that pulses the detection laser.
11. pulseFrequency(Hz) - zero unless the mouse uses polledActuation
    * How often the mouse checks to see if there was a click
    * This measurement can only be taken with an oscilloscope
12. actuationDetectionDuration(us) - the amount of time the mouse will accept a click per cycle.
    * For optical mice, this is the amount of time the detection light / laser is on
13. maximumHostPollRate(Hz) - maximum polling rate supported by the mouse
14. avgLmbLatency(us) - average latency of 500 clicks
15. stdDev(us) - standard deviation of 500 clicks
16. adjustedAvgLmbLatency(us) - ((1000 \* (pulseFrequency /
    maximumHostPollRate) - actuationDetectionDuration) / 2) +
    avgLMBLatency
17. testedBy - who tested the mouse
    * NVIDIA only for now

**Mouse brand workbook tabs**

*  Mice brands that have three or more tested mice should have their own worksheet tab.

*  Each column represents mouse make, model, minimum, maximum, average, standard devviation, and 500 recorded left mouse button click latencies.

## **Example**

   | **Columns** | **Values**|
   |-----------------------------------|--------------------------|
   |**make**                           |Logitech G  
   |**model**                          |PRO X SUPERLIGHT (wired)|
   |**vid**                            |046d|
   |**pid**                            |c094|
   |**revision**                       |2500|
   |**mode**                           |wired|
   |**type**                           |none|
   |**reportExtensionId**              |FALSE|
   |**perClickLatency**                |TRUE|
   |**polledActuation**                |FALSE|
   |**pulseFrequencyHz**               |0|
   |**actuationDetectionDurationHz**   |0|
   |**maximumHosePollRateHz**          |1000|
   |**avgLmbLatencyUs**                |808|
   |**stdDevUs**                       |302|
   |**adjustedAvgLmbLatencyUs**        |808|
   |**TestedBy**                      |NVIDIA|

## **Licensing**

By contributing to this document the contributor acknowledges that that
all contributions are licensed under [CC BY4.0](https://creativecommons.org/licenses/by/4.0/).

## **Additional Information**

[**NVIDIA Reflex**](https://www.nvidia.com/en-us/geforce/news/reflex-low-latency-platform/)

[**Mouse Partner** ](https://developer.nvidia.com/reflex-mice-partner-program-interest)
