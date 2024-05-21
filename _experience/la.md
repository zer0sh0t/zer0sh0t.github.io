---
layout: page
title: Lycan Automotive
description: <p>Software Engineer<br>May 2021 - Jan 2022<br>Bangalore, India</p>
img: assets/img/carla.jpeg
importance: 2
---

Tools used: Python, C/C++, Git, Ubuntu, Tensorflow, PyTorch, NumPy, OpenCV, ROS, CARLA

<div class="row mt-3">
    {% include figure.liquid loading="eager" path="assets/img/carla.jpeg" class="img-fluid rounded z-depth-1" zoomable=true %}
</div>
<div class="caption">
    Figure 1: CARLA simulator
</div>

My task was to develop algorithms for a fully self-driving car capable of navigating Indian streets. We gathered some data ourselves and also utilized open-source datasets such as KITTI and UCB. To achieve this goal, I employed various deep learning models and simulators, including CARLA, Highway Env, and a custom-made simulator. Ultimately, I developed and optimized single-stage and multi-stage monocular 3D object detection algorithms using PyTorch and Numba, achieving an impressive mean average precision of 87%.

<div class="row mt-3">
    {% include video.liquid path="assets/video/3d_obj.mp4" class="img-fluid rounded z-depth-1" controls=true autoplay=false %}
</div>
<div class="caption">
    Video 1: 3D object detection system in CARLA simulator
</div>

I utilized OpenCV and TensorFlow to create robust lane detection systems capable of accurately identifying and distinguishing all road lanes, achieving an impressive accuracy rate of 84%. Additionally, I developed an advanced collision avoidance algorithm that effectively prevents collisions with both vehicles and pedestrians, attaining a success rate of 95%.

<div class="row mt-3">
    {% include figure.liquid loading="eager" path="assets/img/lane_det.png" class="img-fluid rounded z-depth-1" zoomable=true %}
</div>
<div class="caption">
    Figure 2: Shows the output of lane detection system on real-time camera feed
</div>

<div class="row mt-3">
    <div class="col-sm mt-3 mt-md-0">
        {% include video.liquid path="assets/video/obs_avo_1.mp4" class="img-fluid rounded z-depth-1" controls=true autoplay=false %}
    </div>
</div>
<div class="caption">
    Video 2: Demonstration of collision avoidance algorithm in a 2d highway environment
</div>

Using the proposed approaches, I developed a proof of concept for a self-driving car that operates within a custom-made simulator, which successfully secured our initial funding.
