---
layout: page
title: Revolute Robotics
role: Senior Robotics Engineer, previously Control Systems Engineer
period: Feb 2025 – Jul 2026
location: Boston, MA
order: 1
description: Senior Robotics Engineer · Feb 2025 – Jul 2026 · Boston, MA
blurb: "Owned autonomy for GRIFFIN, a robot that drives and flies through industrial spaces people should not enter. Took it from bench to production and put it in front of customers at six sites."
img: assets/img/revolute_hmr.jpg
thumb: assets/img/thumb_revolute.gif
importance: 1
---

## A robot that drives and flies

Inside a pressure vessel, a cooling tower or a run of pipe, there is no GPS, no room to manoeuvre, and no good reason to send a person. The Hybrid Mobility Robot drives when the floor allows it and flies when it does not, inside a cage that lets it bounce off the walls it is inevitably going to hit.

<div class="row justify-content-center mt-3">
    <div class="col-sm-9">
        {% include figure.liquid loading="eager" path="assets/img/revolute_hmr.jpg" class="img-fluid rounded z-depth-1" zoomable=true %}
    </div>
</div>
<div class="caption">
    The HMR: tracks on the outside, four ducted rotors inside the frame
</div>

I joined as a control systems engineer and left as the senior robotics engineer who owned autonomy for GRIFFIN, the production release of the platform. Two versions of the robot, and the whole path from a bench prototype to hardware that customers ran on their own sites.

## Flying inside the plant

This is the part that is hard to argue with. The robot holding position and moving through a live industrial structure, walls on every side and no satellite fix anywhere in the building.

<div class="row justify-content-center mt-3">
    <div class="col-sm-10">
        {% include video.liquid path="assets/video/revolute_flight.mp4" class="img-fluid rounded z-depth-1" controls=true autoplay=false %}
    </div>
</div>
<div class="caption">
    GRIFFIN flying between structural steel and pipe runs on site
</div>

## Knowing where you are with no GPS

Everything above depends on the robot knowing its own position, and it cannot ask a satellite. I led integration and algorithm development for a LiDAR-IMU localization and mapping stack that holds cumulative pose drift to 1 cm over a 100 m traverse, with loop closure landing in 50 ms.

<div class="row justify-content-center mt-3">
    <div class="col-sm-10">
        {% include video.liquid path="assets/video/revolute_slam.mp4" class="img-fluid rounded z-depth-1" controls=true autoplay=false %}
    </div>
</div>
<div class="caption">
    SLAM replayed from a ROS bag. White is the feature points in the current scan, colour is the map they are matched into.
</div>

One centimetre over a hundred metres is the difference between a map an inspector can act on and a map that is merely a nice picture. The perception stack fuses LiDAR SLAM, visual SLAM, micro-ToF and RGB; planning and control run on ArduPilot and MavROS.

Field crews needed to trust it too, so I put real-time point cloud visualisation and map quality feedback into the operator workflow. Inspection coverage gets verified before anyone packs up and drives home, not a week later at a desk.

<div class="row justify-content-center mt-3">
    <div class="col-sm-10">
        {% include video.liquid path="assets/video/revolute_drive.mp4" class="img-fluid rounded z-depth-1" controls=true autoplay=false %}
    </div>
</div>
<div class="caption">
    Driving mode over broken ground, with the live map building underneath
</div>

## Rebuilding the platform

Before any of that worked, it had to be made to work. In my first month I rebuilt eight subsystems across software, firmware, control, sensing and the mechatronic architecture, then took the platform through five hardware and software revisions.

Two changes mattered most. I wrote custom firmware for an MPC-based locomotion mode and tuned the PID gains against logged data, cutting energy per manoeuvre by 30%. Then I re-engineered the powertrain across motor drives, gear ratios and battery management for a 30% better thrust-to-weight ratio, which is what buys payload and endurance on a robot that has to lift itself.

<div class="row justify-content-center mt-3">
    <div class="col-sm-7">
        {% include figure.liquid loading="eager" path="assets/img/revolute_build.jpg" class="img-fluid rounded z-depth-1" zoomable=true %}
    </div>
</div>
<div class="caption">
    An earlier HMR on the bench
</div>

## Out of the lab

A robot that works in the lab is a demo. I led field deployments at six customer sites, including Palo Verde, the largest nuclear plant in the United States, and a coal mine outside Phoenix. Pre-deployment validation, flight testing on site, and diagnosing failures on someone else's schedule with the crew standing there watching.

<div class="row justify-content-center mt-3">
    <div class="col-sm-9">
        {% include figure.liquid loading="eager" path="assets/img/revolute_mine.jpg" class="img-fluid rounded z-depth-1" zoomable=true %}
    </div>
</div>
<div class="caption">
    Underground in the mine
</div>

Across 30 days of field operation the robot flew reliably inside live tanks, towers and pipe runs.

## Shipping a fleet

Production is its own engineering problem. I owned project planning and the production ramp for the fleet, coordinating a five-person build team across seven HMR units and cutting build-to-field turnaround by three weeks.

<div class="row justify-content-center mt-3">
    <div class="col-sm-10">
        {% include figure.liquid loading="eager" path="assets/img/revolute_team.jpg" class="img-fluid rounded z-depth-1" zoomable=true %}
    </div>
</div>
<div class="caption">
    Part of the team, with the robots that shipped
</div>
