---
layout: page
title: Lycan Automotive
role: Software Engineer
period: Mar 2021 – Feb 2022
location: Bangalore, India
description: Software Engineer · Mar 2021 – Feb 2022 · Bangalore, India
blurb: Perception and planning for an autonomous EV aimed at Indian traffic. The prototype I built raised the company's first round.
img: assets/img/3d_obj.gif
importance: 2
---

## The problem

Lycan was building consumer EVs for Indian roads. Unstructured traffic, unmarked lanes, and pedestrians who negotiate rather than wait — the benchmarks trained on Californian highways do not transfer.

I built the perception and planning stack that had to survive it, across CARLA, Highway Env, and a custom simulator, trained on a mix of our own data and KITTI and UCB.

<div class="row mt-3">
    {% include figure.liquid loading="eager" path="assets/img/carla.jpeg" class="img-fluid rounded z-depth-1" zoomable=true %}
</div>
<div class="caption">
    CARLA simulator
</div>

## 3D object detection

Single-stage and multi-stage monocular 3D detection in PyTorch and Numba — vehicles, pedestrians, cyclists, trucks — at 87% mAP, from a single camera and no lidar.

<div class="row mt-3">
    {% include video.liquid path="assets/video/3d_obj.mp4" class="img-fluid rounded z-depth-1" controls=true autoplay=false %}
</div>
<div class="caption">
    3D object detection in CARLA
</div>

## Lane detection

84% accuracy on real-time camera feed, on roads where the lane markings are frequently a suggestion.

<div class="row mt-3">
    {% include figure.liquid loading="eager" path="assets/img/lane_det.png" class="img-fluid rounded z-depth-1" zoomable=true %}
</div>
<div class="caption">
    Lane detection on a live camera feed
</div>

## Collision avoidance

A planner in Highway Env that avoids vehicles and pedestrians at a 95% success rate.

<div class="row mt-3">
    {% include video.liquid path="assets/video/obs_avo.mp4" class="img-fluid rounded z-depth-1" controls=true autoplay=false %}
</div>
<div class="caption">
    Collision avoidance in a 2D highway environment
</div>

## Outcome

I assembled the pieces into a self-driving proof of concept in a custom simulator. It secured the company's first funding round.
