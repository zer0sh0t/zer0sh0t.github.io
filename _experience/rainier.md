---
layout: page
title: Rainier Labs
role: Research Engineer
period: Oct 2024 – Jan 2025
location: San Jose, CA
order: 5
description: Research Engineer · Oct 2024 – Jan 2025 · San Jose, CA
blurb: "Built the locomotion controller for the Terrier quadruped from prototype, taking it from a policy trained across 4000 simulated robots to one that walks on hardware."
img: assets/img/rainier_dog.jpg
thumb: assets/img/thumb_rainier.gif
importance: 3
---

## Terrier

Terrier is a quadruped, and when I arrived it was a prototype that could not yet walk. I built its locomotion controller, working both sides of the problem at once: classical control for what could be derived, deep reinforcement learning for what could not.

<div class="row justify-content-center mt-3">
    <div class="col-sm-7">
        {% include figure.liquid loading="eager" path="assets/img/rainier_humanoid.jpg" class="img-fluid rounded z-depth-1" zoomable=true %}
    </div>
</div>
<div class="caption">
    Terrier in the lab
</div>

## Learning to walk

Gaits are hard to hand-write and easy to learn badly. I architected the training environments in NVIDIA Isaac Sim and wrote the Proximal Policy Optimization routine that ran in them, with 4000 Terriers spawned in parallel, all failing and correcting at once.

<div class="row justify-content-center mt-3">
    <div class="col-sm-10">
        {% include video.liquid path="assets/video/rainier_sim.mp4" class="img-fluid rounded z-depth-1" autoplay=true loop=true muted=true controls=false %}
    </div>
</div>
<div class="caption">
    Training in Isaac Sim, 4000 robots learning in parallel
</div>

The routine converged within 12,000 episodes and lifted stable-gait success from 30% to 85%. I trained and evaluated policies across five terrain types including slopes, gravel and stairs, and the policies held 80% gait stability on surfaces they had never seen in training, which is the number that says the controller learned to walk rather than to memorize a floor.

## Onto the hardware

A policy that works in simulation has proven nothing. I deployed the trained policy to the physical robot and validated it across more than 30 hardware-in-the-loop trials, where it held the same 85% stable-gait success it reached in simulation.

<div class="row justify-content-center mt-3">
    <div class="col-sm-8">
        {% include figure.liquid loading="eager" path="assets/img/rainier_rig.jpg" class="img-fluid rounded z-depth-1" zoomable=true %}
    </div>
</div>
<div class="caption">
    Terrier on the test gantry, where every policy had to survive before it ran free
</div>

## Off the tether

<div class="row justify-content-center mt-3">
    <div class="col-sm-10">
        {% include video.liquid path="assets/video/rainier_terrier.mp4" class="img-fluid rounded z-depth-1" controls=true autoplay=false %}
    </div>
</div>
<div class="caption">
    Terrier walking untethered, among people and one unimpressed dog
</div>

The last test is not a benchmark. It is a crowded room, a hard floor, and a real dog that has opinions about what a four-legged thing should move like.

<div class="row justify-content-center mt-3">
    <div class="col-sm-7">
        {% include figure.liquid loading="eager" path="assets/img/rainier_dog.jpg" class="img-fluid rounded z-depth-1" zoomable=true %}
    </div>
</div>
<div class="caption">
    Peer review
</div>
