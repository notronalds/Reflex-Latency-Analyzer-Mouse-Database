**NVIDIA Reflex Latency Analyzer Mice Database**

**Purpose**

NVIDIA Reflex is about end to end system latency which includes
peripheral latency such as mice. Our objective is to collect mice data
to provide gamers their current mouse latency when using a mouse listed
in the database. The mice that are entered into the database are
recognized by GeForce Experience and their latency statistics can be
displayed within the latency overlay.

**Contents**

This repository contains an Excel Workbook consisting of popular Esports
mice, mice attributes, and left mouse button click latency.

**Components**

1.  Public Mouse DB tab

    a.  Make

    b.  Mode

    c.  VID - vendor ID

    d.  PID - product ID

    e.  Revision - firmware version tested

    f.  Mode - wired / wireless

    g.  Type - wired / wireless, reported through the RLA

        -   This will typically be "none"

    h.  reportExtensionId - true if the mouse reports PID, VID, and
        > Revision extension

    i.  perClickLatency - true if the mouse firmware implements per
        > click latency

    j.  polledActuation - true if the mouse uses polled actuation

        -   An example of this is an optical switch

    k.  pulseFrequency(Hz) - zero unless the mouse uses polledActuation

        -   This measurement can only be taken with an oscilloscope

    l.  actuationDetection(us) - time it takes for the mouse to check
        > for polled actuation

        -   For optical mice, this is the amount of time the light /
            > laser is on

    m.  maximumHostPollRate(Hz) - maximum polling rate supported by the
        > mouse

    n.  avgLmbLatency(us) - average latency of 500 clicks

    o.  stdDev(us) - standard deviation of 500 clicks

    p.  adjustedAvgLmbLatency(us) - (1000 \* (pulseFrequency /
        > maximumHostPollRate)) / 2 + actuationDetectionDuration

    q.  testedBy - who tested the mouse

        -   NVIDIA only for now

2.  Mouse brand workbook tabs

    a.  Mice brands that have three or more tested mice should have
        > their own worksheet tab.

    b.  Each column represents mouse make, model, minimum, maximum,
        > average, standard deviation, and 500 recorded left mouse
        > button click latencies.

**Licensing**

By contributing to this document the contributor acknowledges that that
all contributions are licensed under [[CC BY
4.0]{.ul}](https://creativecommons.org/licenses/by/4.0/).
