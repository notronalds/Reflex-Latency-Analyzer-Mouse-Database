**NVIDIA Reflex Latency Analyzer Mice Database**

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

**Contents**

This repository contains an Excel Workbook consisting of popular Esports
mice, mice attributes, and left mouse button click latency.

**Components**

1.  Mouse DB tab

    a.  Make- brand

    b.  Mode - product

    c.  VID - vendor ID

    d.  PID - product ID

    e.  Revision - firmware version tested (BCD Device ID)

    f.  Mode - wired / wireless

        -   Whether the mouse is operating wired or wirelessly.

    g.  Type - wired / wireless, reported through the USB Extension

        -   Implemented by the mouse manufacturer

        -   This field can be "none" if the vendor is not using our
            > extension

    h.  reportExtensionId - true if the mouse reports PID, VID, and
        > Revision extension

        -   This is used by the mouse vendor to indicate a different PID
            > and Revision in cases where the device connected to the PC
            > is a dongle or intermediate device.

    i.  perClickLatency - true if the mouse firmware implements per
        > click latency

    j.  polledActuation - true if the mouse uses polled actuation

        -   An example of this is an optical switch that pulses the
            > detection laser.

    k.  pulseFrequency(Hz) - zero unless the mouse uses polledActuation

        -   How often the mouse checks to see if there was a click

        -   This measurement can only be taken with an oscilloscope

    l.  actuationDetectionDuration(us) - the amount of time the mouse
        > will accept a click per cycle.

        -   For optical mice, this is the amount of time the detection
            > light / laser is on

    m.  maximumHostPollRate(Hz) - maximum polling rate supported by the
        > mouse

    n.  avgLmbLatency(us) - average latency of 500 clicks

    o.  stdDev(us) - standard deviation of 500 clicks

    p.  adjustedAvgLmbLatency(us) - ((1000 \* (pulseFrequency /
        > maximumHostPollRate) - actuationDetectionDuration) / 2) +
        > avgLMBLatency

    q.  testedBy - who tested the mouse

        -   NVIDIA only for now

2.  Mouse brand workbook tabs

    a.  Mice brands that have three or more tested mice should have
        > their own worksheet tab.

    b.  Each column represents mouse make, model, minimum, maximum,
        > average, standard deviation, and 500 recorded left mouse
        > button click latencies.

**Example**

  **make**                           Logitech G
  ---------------------------------- --------------------------
  **model**                          PRO X SUPERLIGHT (wired)
  **vid**                            046d
  **pid**                            c094
  **revision**                       2500
  **mode**                           wired
  **type**                           none
  **reportExtensionId**              FALSE
  **perClickLatency**                TRUE
  **polledActuation**                FALSE
  **pulseFrequencyHz**               0
  **actuationDetectionDurationHz**   0
  **maximumHosePollRateHz**          1000
  **avgLmbLatencyUs**                808
  **stdDevUs**                       302
  **adjustedAvgLmbLatencyUs**        808
  **Tested By**                      NVIDIA

**Licensing**

By contributing to this document the contributor acknowledges that that
all contributions are licensed under [[CC BY
4.0]{.ul}](https://creativecommons.org/licenses/by/4.0/).

**Additional Information**

[[NVIDIA
Reflex]{.ul}](https://www.nvidia.com/en-us/geforce/news/reflex-low-latency-platform/)

[[Mouse Partner
Program]{.ul}](https://developer.nvidia.com/reflex-mice-partner-program-interest)
