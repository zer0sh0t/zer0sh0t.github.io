---
layout: page
title: Silicon Synapse Lab
role: Research Assistant
period: Mar 2023 – Apr 2024
location: Boston, MA
order: 3
description: Research Assistant · Mar 2023 – Apr 2024 · Boston, MA
blurb: "Perception, controls and autonomy for three robots: COBRA, the NASA-funded snake robot that took the Artemis Award, Harpy, a thruster-assisted biped built with Caltech, and Husky, a quadruped that flies."
img: assets/img/cobra_neu_0.gif
thumb: assets/img/thumb_ss.gif
importance: 1
---

## COBRA

COBRA, short for Crater Observing Bio-inspired Rolling Articulator, has eleven joints, twelve links, and no wheels. It sidewinds, rolls, and tumbles into lunar craters that rovers cannot enter, hunting the frozen water suspected at the bottom of them.

The project is NASA-funded and took first place at the NASA BIG Idea Challenge, earning the Artemis Award. I led development of its simulation software and the controllers that ran on it.

<div class="row mt-3">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/sidewinding.gif" class="img-fluid rounded z-depth-1" zoomable=true %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/cobra_modes.png" class="img-fluid rounded z-depth-1" zoomable=true %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/sidewinding_sheath.gif" class="img-fluid rounded z-depth-1" zoomable=true %}
    </div>
</div>
<div class="row mt-3">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/locoman_0_small.gif" class="img-fluid rounded z-depth-1" zoomable=true %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/cobra.png" class="img-fluid rounded z-depth-1" zoomable=true %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/locoman_1.gif" class="img-fluid rounded z-depth-1" zoomable=true %}
    </div>
</div>
<div class="row mt-3">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/hex.gif" class="img-fluid rounded z-depth-1" zoomable=true %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/cobra_neu_0.gif" class="img-fluid rounded z-depth-1" zoomable=true %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/tumbling.gif" class="img-fluid rounded z-depth-1" zoomable=true %}
    </div>
</div>
<div class="caption">
    COBRA across its locomotion modes
</div>

<div class="row mt-3">
    {% include figure.liquid loading="eager" path="assets/img/cobra_model.png" class="img-fluid rounded z-depth-1" zoomable=true %}
</div>
<div class="caption">
    Coordinate frames and parameters used to model COBRA
</div>

## Model Matching

Simulators lie. The gap between COBRA in Webots and COBRA on sand was wide enough to make simulation useless for designing controllers.

So I stopped tuning the robot and started tuning the simulator. Model Matching is a reinforcement learning loop that treats the simulator's own parameters (friction coefficients, actuator dynamics) as the thing to be optimized, fitting them against trajectories recorded from the hardware. It closed the sim-to-real gap by over 90%.

<div class="row mt-3">
    {% include figure.liquid loading="eager" path="assets/img/model_matching.png" class="img-fluid rounded z-depth-1" zoomable=true %}
</div>
<div class="caption">
    The model matching framework
</div>

I built the tuning API across both Webots and MuJoCo, and an accelerated training pipeline that quadrupled throughput.

<div class="row mt-3">
    {% include video.liquid path="assets/video/real_untuned_tuned_text.mp4" class="img-fluid rounded z-depth-1" controls=true autoplay=false %}
</div>
<div class="caption">
    Sidewinding in Webots: tuned model (right) against untuned (center). The red ball marks where the real robot ended up under the same joint trajectories.
</div>

<div class="row mt-3">
    {% include figure.liquid loading="eager" path="assets/img/head_trajectories.png" class="img-fluid rounded z-depth-1" zoomable=true %}
</div>
<div class="caption">
    Head position in hardware (red), tuned model (blue), untuned model (green), sidewinding at 0.35, 0.5 and 0.65 Hz
</div>

<div class="row mt-3">
    {% include figure.liquid loading="eager" path="assets/img/joint_angle_comparison.png" class="img-fluid rounded z-depth-1" zoomable=true %}
</div>
<div class="caption">
    Actuator joint response, hardware (red) against tuned (blue) and untuned (green), sidewinding at 0.5 Hz
</div>

## Loco-manipulation

A snake has no arms. It manipulates objects by locomoting around them, which means locomotion and manipulation stop being separable problems and have to be solved at once.

I built the controller that does it. 94.3% success rate, with dynamic replanning when the target moves mid-execution.

<div class="row mt-3">
    <div class="col-sm mt-3 mt-md-0">
        {% include video.liquid path="assets/video/locoman.mp4" class="img-fluid rounded z-depth-1" controls=true autoplay=false %}
    </div>
</div>
<div class="caption">
    COBRA performing loco-manipulation
</div>

<div class="row mt-3">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/locoman_sim.png" class="img-fluid rounded z-depth-1" zoomable=true %}
    </div>
</div>
<div class="caption">
    Problem setup in Webots
</div>

<div class="row mt-3">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/locomancon.png" class="img-fluid rounded z-depth-1" zoomable=true %}
    </div>
</div>
<div class="caption">
    Hierarchical structure of the loco-manipulation controller
</div>

<div class="row mt-3">
    <div class="col-sm mt-3 mt-md-0">
        {% include video.liquid path="assets/video/loco_ex4.mp4" class="img-fluid rounded z-depth-1" controls=true autoplay=false %}
    </div>
</div>
<div class="caption">
    Controller running in Webots (2x)
</div>

<div class="row mt-3">
    <div class="col-sm mt-3 mt-md-0">
        {% include video.liquid path="assets/video/loco_ex2.mp4" class="img-fluid rounded z-depth-1" controls=true autoplay=false %}
    </div>
</div>
<div class="caption">
    Controller running in Webots (2x)
</div>

<div class="row mt-3">
    {% include video.liquid path="assets/video/loco_ex5.mp4" class="img-fluid rounded z-depth-1" controls=true autoplay=false %}
</div>
<div class="caption">
    Dynamic replanning (2x). The object is moved to a random position mid-execution.
</div>

## Harpy

Harpy is a thruster-assisted bipedal robot, built with Caltech. Thrusters make the energy budget the binding constraint, so I framed trajectory planning as an RL problem and led the team through the formulation: navigating obstacles to a goal while minimizing power draw.

<div class="row mt-3">
    {% include figure.liquid loading="eager" path="assets/img/harpy.png" class="img-fluid rounded z-depth-1" zoomable=true %}
</div>
<div class="caption">
    Harpy
</div>

<div class="row mt-3">
    {% include figure.liquid loading="eager" path="assets/img/harpy_rl.png" class="img-fluid rounded z-depth-1" zoomable=true %}
</div>
<div class="caption">
    Environment setup in Webots
</div>

## Husky

Husky is a quadruped that also flies. That makes every step a decision: walk over the terrain ahead, or spend battery and fly across it. The robot cannot make that call without reading the ground first.

<div class="row mt-3">
    {% include figure.liquid loading="eager" path="assets/img/husky.jpg" class="img-fluid rounded z-depth-1" zoomable=true %}
</div>
<div class="caption">
    Husky, a multi-modal quadruped with ducted-fan propulsion
</div>

I built a deep learning elevation mapping pipeline that fuses the onboard RGBD cameras and lidar into a 2.5D elevation map, estimates traversability from it in real time, and turns that into a costmap the planner uses to choose between walking and flight.

<div class="row justify-content-center mt-3">
    <div class="col-sm-10">
        {% include video.liquid path="assets/video/husky_elevation.mp4" class="img-fluid rounded z-depth-1" controls=true autoplay=false %}
    </div>
</div>
<div class="caption">
    Elevation map built live from onboard sensing, with the robot's view insets
</div>

The pipeline started on M4, a wheeled multi-modal platform. I reworked and migrated it to Husky, retuning it for quadrupedal dynamics, where the gait moves the sensors and the ground contact is intermittent.

<div class="row mt-3">
    {% include figure.liquid loading="eager" path="assets/img/husky_pipeline.png" class="img-fluid rounded z-depth-1" zoomable=true %}
</div>
<div class="caption">
    Perception and navigation pipeline, as originally structured for M4
</div>

<div class="row justify-content-center mt-3">
    <div class="col-sm-10">
        {% include video.liquid path="assets/video/husky_walk.mp4" class="img-fluid rounded z-depth-1" autoplay=true loop=true muted=true controls=false %}
    </div>
</div>
<div class="caption">
    Husky walking under the migrated stack
</div>

## Further reading

Full thesis: [Reinforcement learning-based model matching in COBRA](https://doi.org/10.17760/D20659774). Short version: [the blog post]({{ '/blog/2024/my-thesis/' | relative_url }}).

## References

[1] "Reinforcement learning-based model matching in COBRA, a slithering snake robot" by Harin Kumar Nallaguntla (2024). [https://doi.org/10.17760/D20659774](https://doi.org/10.17760/D20659774)

[2] [Rovers Are So Yesterday. It's Time to Send a Snakebot to Space](https://www.wired.com/story/rovers-are-so-yesterday-its-time-to-send-a-snakebot-to-space/), WIRED

[3] [Northeastern University Slithers to the Top with BIG Idea Alternative Rover Concept](https://www.nasa.gov/directorates/stmd/northeastern-university-slithers-to-the-top-with-big-idea-alternative-rover-concept/), NASA

[4] [Northeastern University 2022 BIG Idea Technical Paper](https://bigidea.nianet.org/wp-content/uploads/Northeastern-University-2022-Big-Idea-Technical-Paper.pdf)

[5] "Non-impulsive Contact-Implicit Motion Planning for Morpho-functional Loco-manipulation" by A. Salagame et. al (2024). [https://arxiv.org/abs/2404.08714](https://arxiv.org/abs/2404.08714)

[6] "Loco-Manipulation with Nonimpulsive Contact-Implicit Planning in a Slithering Robot" by A. Salagame et. al (2024). [https://arxiv.org/abs/2404.08174](https://arxiv.org/abs/2404.08174)

[7] "Dynamic Multimodal Locomotion: A Quick Overview of Hardware and Control" by Shreyansh Pitroda (2023). [https://arxiv.org/abs/2310.00008](https://arxiv.org/abs/2310.00008)

[8] "How Strong a Kick Should be to Topple Northeastern's Tumbling Robot?" by A. Salagame et. al (2023). [https://arxiv.org/abs/2311.14878](https://arxiv.org/abs/2311.14878)

[9] [Field testing COBRA at the NASA BIG Idea Forum 2022](https://www.youtube.com/watch?v=Zv2XgsOK-Tg&ab)

[10] [https://www.youtube.com/watch?v=8cmpR3J5gbY&ab](https://www.youtube.com/watch?v=8cmpR3J5gbY&ab)
