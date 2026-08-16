---
layout: page
title: Lookout
role: Software Engineer, Sensors and Integration
period: Aug 2024 – Feb 2025
location: Cambridge, MA
order: 1
description: Software Engineer, Sensors and Integration · Aug 2024 – Feb 2025 · Cambridge, MA
blurb: Perception and planning for a fleet of 70 autonomous surface vessels running with the US Coast Guard, the US Navy and commercial operators.
img: assets/img/lookout_system.jpg
thumb: assets/img/thumb_lookout.jpg
importance: 2
---

## Autonomy for boats

A boat has no lanes, no signage and no brakes. Traffic negotiates by convention, the sea state changes what the sensors see, and stopping distance is measured in boat lengths. Lookout builds the perception system that watches for all of it, and I worked on the part that has to see and decide.

The stack ships as a camera mast, an NVIDIA compute box below deck, and an overlay on the chartplotter the helm is already looking at.

<div class="row justify-content-center mt-3">
    <div class="col-sm-8">
        {% include figure.liquid loading="eager" path="assets/img/lookout_system.jpg" class="img-fluid rounded z-depth-1" zoomable=true %}
    </div>
</div>
<div class="caption">
    The deployed system: camera, compute, and an augmented view on the helm display
</div>

## Perception

I extended the perception stack to fuse RADAR, RGB and thermal cameras, GPS and IMU into a single picture of the water. It holds 98% detection and tracking accuracy across 15 object classes out to a kilometre, which is the range that matters when closing speeds are high and course changes are slow.

<div class="row justify-content-center mt-3">
    <div class="col-sm-10">
        {% include video.liquid path="assets/video/lookout_demo.mp4" class="img-fluid rounded z-depth-1" controls=true autoplay=false %}
    </div>
</div>
<div class="caption">
    Detections and tracks overlaid on the live camera feed, underway
</div>

## Planning

Open water is not a road network, so I designed an enhanced RRT* planner shaped around boat dynamics: no instant heading changes, no reversing out of a mistake. It replans in 70 ms and clears cluttered traffic 96% of the time across varying sea states.

## Making it run on the boat

None of it matters if it does not fit in the box on the vessel. I optimized the end-to-end pipeline for embedded deployment and held 60 Hz on a Jetson Orin while cutting CPU load by 25%, memory by 20%, and operating temperature by 15%, which is what keeps hardware alive in an engine bay in summer.

The result runs on a fleet of 70 vessels operated by the US Coast Guard, the US Navy and commercial marine operators.
