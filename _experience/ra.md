---
layout: page
title: Research Assistant
description: <p>SiliconSynapse Lab<br>Apr 2023 - Present</p>
img: assets/img/cobra.png
importance: 1
---

Tools used: Python, MATLAB, Simscape, C/C++, Git, Ubuntu, PyTorch, Gazebo, Webots

<div class="row mt-3">
    {% include figure.liquid loading="eager" path="assets/img/cobra.png" class="img-fluid rounded z-depth-1" zoomable=true %}
</div>
<div class="caption">
    Figure 1: COBRA robot
</div>

COBRA, which stands for Crater Observing Bio-inspired Rolling Articulator, is a snake-like robot designed to mimic the movement of serpentine creatures. Created to navigate challenging terrains such as craters—where traditional robots often face difficulties—COBRA is equipped with 11 joints and 12 links, enabling intricate and versatile movements. With 6 yawing and 5 pitching joints, it offers a wide range of orientations, making it ideal for various robotic applications.

I led the development and maintenance of simulation software for COBRA, an innovative morpho-functional snake robot. Our team secured $1M funding from NASA to support lunar surface exploration initiatives.

<div class="row mt-3">
    {% include video.liquid path="assets/video/sidewinding.mp4" class="img-fluid rounded z-depth-1" controls=true autoplay=false %}
</div>
<div class="caption">
    Video 1: Shows COBRA performing sidewinding motion
</div>

My work primarily focused on addressing the simulation-to-reallity gap observed with the COBRA platform. I developed a reinforcement learning-based framework called "Model Matching". This framework fine-tunes the simulator model to minimize the discrepancies between the real robot and its simulated counterpart in the Webots simulator, using data from the actual robot. As a result, the fidelity of the Webots simulator has significantly improved.

As part of the model matching framework, I designed a seamless and intuitive API for Webots and MuJoCo simulators, ensuring effective fine-tuning of simulation parameters using Reinforcement Learning (RL) techniques and developed an accelerated Reinforcement Learning model training pipeline, resulting in 4x increase in model training capacity, thereby substantially expediting prototyping and deployment processes. As a result of the model matching framework, sim-to-reality gap has reduced by over 150%, significantly enhancing accuracy and fidelity of COBRA’s locomotion simulations.

<div class="row mt-3">
    {% include video.liquid path="assets/video/real_untuned_tuned_text.mp4" class="img-fluid rounded z-depth-1" controls=true autoplay=false %}
</div>
<div class="caption">
    Video 2:  Shows COBRA in Webots simulator with tuned model (right) and untuned model (center) performing the sidewinding motion. The red ball shows the location the actual robot achieved when similar joint trajectories were applied.
</div>

Video 2 shows the final tuned simulator model I obtained using the model matching framework. As we can see, the tuned simulator model matches closely to the reality.

<div class="row mt-3">
    <div class="col-sm mt-3 mt-md-0">
        {% include video.liquid path="assets/video/locoman.mp4" class="img-fluid rounded z-depth-1" controls=true autoplay=false %}
    </div>
</div>
<div class="caption">
    Video 3: Shows COBRA performing loco-manipulation
</div>

Additionally, Designed novel RL-guided locomotion patterns tailored for seamless object manipulation, leveraging COBRA’s unique body
design to enhance dexterity and precision. Loco-manipulation involves the robot performing locomotion to manipulate objects in its environment, a complex challenge as it requires solving both locomotion and manipulation simultaneously. With the proposed controller, COBRA achieved an impressive success rate of 94.3% in loco-manipulation tasks.

<div class="row mt-3">
    {% include video.liquid path="assets/video/loco_ex4.mp4" class="img-fluid rounded z-depth-1" controls=true autoplay=false %}
</div>
<div class="caption">
    Video 5: Demonstration of the loco-manipulation controller in webots simualtor (played in 2x)
</div>

<div class="row mt-3">
    {% include video.liquid path="assets/video/loco_ex5.mp4" class="img-fluid rounded z-depth-1" controls=true autoplay=false %}
</div>
<div class="caption">
    Video 6: Demonstration of dynamic replanning capabilites of the controller (played in 2x). The object is relocated within the Webots simulator, shifting from its current position to a randomly chosen spot.
</div>
