---
layout: page
title: Lycan Automotive
description: <p>Software Engineer<br>May 2021 - Jan 2022<br>Bangalore, India</p>
img: assets/img/carla.jpeg
importance: 2
---

Tools used: Python, C/C++, Git, Ubuntu, Tensorflow, PyTorch, NumPy, OpenCV, ROS, CARLA

## Lycan Automotive and Autonomous Vehicles

<div class="row mt-3">
    {% include figure.liquid loading="eager" path="assets/img/carla.jpeg" class="img-fluid rounded z-depth-1" zoomable=true %}
</div>
<div class="caption">
    Figure 1: CARLA simulator
</div>

Lycan Automotive, a Bangalore-based startup, is focused on creating electric vehicles tailored for consumer markets. In my role, I focused on developing AI algorithms customized for these electric cars, enabling them to navigate India's bustling streets autonomously. To realize the company's vision of autonomous navigation, I utilized a range of deep learning models and simulators like CARLA, Highway Env, and a custom simulator. We gathered some of the data ourselves and also utilized open-source datasets such as KITTI and UCB for training the AI algorithms.

## 3D Object Detection

I developed and optimized single-stage and multi-stage monocular 3D object detection algorithms using PyTorch and Numba to detect vehicles, pedestrians, cyclists, trucks, and more on the road. These algorithms achieved an outstanding mean average precision of 87%, ensuring accurate detection of these objects.

<div class="row mt-3">
    {% include video.liquid path="assets/video/3d_obj.mp4" class="img-fluid rounded z-depth-1" controls=true autoplay=false %}
</div>
<div class="caption">
    Video 1: 3D object detection system in CARLA simulator
</div>

## Lane Detection

Lane detection on roads is essential for maintaining car stability during driving. Using OpenCV and TensorFlow, I developed robust lane detection systems that accurately identify and differentiate all road lanes, achieving an impressive 84% accuracy rate.
<div class="row mt-3">
    {% include figure.liquid loading="eager" path="assets/img/lane_det.png" class="img-fluid rounded z-depth-1" zoomable=true %}
</div>
<div class="caption">
    Figure 2: Shows the output of lane detection system on real-time camera feed
</div>

## Collision Avoidance

Furthermore, I designed an advanced collision avoidance algorithm inside Highway Env simulator that successfully prevents collisions with vehicles and pedestrians, with a remarkable success rate of 95%. Examples of the algorithm behavior is shown below.

<div class="row mt-3">
    {% include video.liquid path="assets/video/obs_avo.mp4" class="img-fluid rounded z-depth-1" controls=true autoplay=false %}
</div>
<div class="caption">
    Video 2: Demonstration of collision avoidance algorithm in a 2d highway environment
</div>

## Acquired Funding

Using the developed approaches, I created a proof of concept for a self-driving car that operates within a custom-made simulator (confidential, not shown here), which successfully secured our initial funding.
