---
layout: page
title: Silicon Synapse Lab
description: <p>Research Assistant<br>Apr 2023 - Present<br>Boston, USA</p>
img: assets/img/cobra_neu_0.gif
importance: 1
---

Tools used: Python, MATLAB, Simscape, C/C++, Git, Ubuntu, PyTorch, Gazebo, Webots, ROS

## COBRA Robot and Lunar Exploration

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
    Figure 1: COBRA robot
</div>

Silicon Synapse Lab specializes in designing bio-inspired robots. COBRA is one such project at SS Lab. COBRA, short for Crater Observing Bio-inspired Rolling Articulator, is a snake-like robot designed to emulate the movement of serpentine creatures. My work focused on enhancing the locomotion and loco-manipulation capabilities of COBRA. Engineered to navigate challenging terrains like craters, where traditional robots often struggle, COBRA features 11 joints and 12 links, enabling intricate and versatile movements. Specifically designed to explore hard-to-navigate lunar craters suspected of containing frozen water, COBRA could significantly contribute to identifying these frozen deposits, paving the way for future lunar colonization.

<div class="row mt-3">
    {% include figure.liquid loading="eager" path="assets/img/cobra_model.png" class="img-fluid rounded z-depth-1" zoomable=true %}
</div>
<div class="caption">
    Figure 2: Shows coordinate frames and parameters usd for modeling COBRA
</div>

I led the development and maintenance of simulation software for COBRA. COBRA team successfully secured $1 million in funding from NASA to support lunar surface exploration initiatives and earned top spot at the 2022 NASA BIG Idea Challenge, receiving the prestigious Artemis Award.

## Model Matching Framework

My work primarily focused on bridging the simulation-to-reality gap in the COBRA platform. I developed a reinforcement learning-based framework called "Model Matching," which fine-tunes the simulator model to reduce discrepancies between the real robot and its simulated counterpart in the Webots simulator. By leveraging data from the actual robot, this framework has significantly enhanced the accuracy and fidelity of COBRA's locomotion simulations in the Webots simulator, reducing the sim-to-reality gap by over 150%.

<div class="row mt-3">
    {% include figure.liquid loading="eager" path="assets/img/model_matching.png" class="img-fluid rounded z-depth-1" zoomable=true %}
</div>
<div class="caption">
    Figure 3: Model matching framework
</div>

As part of the Model Matching framework, I designed a seamless and intuitive API for the Webots and MuJoCo simulators, enabling effective fine-tuning of simulation parameters using reinforcement learning techniques. Additionally, I developed an accelerated RL model training pipeline, resulting in a fourfold increase in training capacity, which substantially expedited the prototyping and deployment processes.

<div class="row mt-3">
    {% include video.liquid path="assets/video/real_untuned_tuned_text.mp4" class="img-fluid rounded z-depth-1" controls=true autoplay=false %}
</div>
<div class="caption">
    Video 1:  Shows COBRA in Webots simulator with tuned model (right) and untuned model (center) performing the sidewinding motion. The red ball shows the location the actual robot achieved when similar joint trajectories were applied.
</div>

<div class="row mt-3">
    {% include figure.liquid loading="eager" path="assets/img/head_trajectories.png" class="img-fluid rounded z-depth-1" zoomable=true %}
</div>
<div class="caption">
    Figure 4: Illustrates a 2D and 3D comparison between the head positions in the actual hardware platform (red), tuned model (blue) and untuned model (green) for a sidewinding trajectory @ 0.35, 0.5, and 0.65 Hz
</div>

<div class="row mt-3">
    {% include figure.liquid loading="eager" path="assets/img/joint_angle_comparison.png" class="img-fluid rounded z-depth-1" zoomable=true %}
</div>
<div class="caption">
    Figure 5: Shows a comparison between the actuator joint responses from the actual hardware platform (red), the tuned (blue) and untuned (green) models for a sidewinding gait @ 0.5 Hz
</div>

Video 1, Fig. 4 and Fig. 5 show results obtained from the final tuned simulator model achieved using the model matching framework. As observed, the tuned simulator model closely matches real-world performance.

## Loco-manipulation Controller

<div class="row mt-3">
    <div class="col-sm mt-3 mt-md-0">
        {% include video.liquid path="assets/video/locoman.mp4" class="img-fluid rounded z-depth-1" controls=true autoplay=false %}
    </div>
</div>
<div class="caption">
    Video 2: Shows COBRA performing loco-manipulation
</div>

Additionally, I developed a controller for loco-manipulation tasks within the Webots simulator. Loco-manipulation involves the robot performing locomotion to manipulate objects in its environment, a complex challenge as it requires solving both locomotion and manipulation simultaneously. With the proposed controller, COBRA achieved an impressive success rate of 94.3% in loco-manipulation tasks, leveraging its unique body design to enhance dexterity and precision.

<div class="row mt-3">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/locoman_sim.png" class="img-fluid rounded z-depth-1" zoomable=true %}
    </div>
</div>
<div class="caption">
    Figure 6: Loco-manipulation problem setup in webots simulator
</div>

<div class="row mt-3">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/locomancon.png" class="img-fluid rounded z-depth-1" zoomable=true %}
    </div>
</div>
<div class="caption">
    Figure 7: Hierarchical structure of loco-manipulation controller
</div>

<div class="row mt-3">
    <div class="col-sm mt-3 mt-md-0">
        {% include video.liquid path="assets/video/loco_ex4.mp4" class="img-fluid rounded z-depth-1" controls=true autoplay=false %}
    </div>
</div>
<div class="caption">
    Video 3: Demonstration of the loco-manipulation controller in webots simualtor (played in 2x)
</div>

<div class="row mt-3">
    <div class="col-sm mt-3 mt-md-0">
        {% include video.liquid path="assets/video/loco_ex2.mp4" class="img-fluid rounded z-depth-1" controls=true autoplay=false %}
    </div>
</div>
<div class="caption">
    Video 4: Demonstration of the loco-manipulation controller in webots simualtor (played in 2x)
</div>

<div class="row mt-3">
    {% include video.liquid path="assets/video/loco_ex5.mp4" class="img-fluid rounded z-depth-1" controls=true autoplay=false %}
</div>
<div class="caption">
    Video 5: Demonstration of dynamic replanning capabilites of the controller (played in 2x). The object is relocated within the Webots simulator, shifting from its current position to a randomly chosen spot.
</div>

## Harpy Robot and RL-based Trajectory Planning

I also led the way in implementing energy-efficient trajectory planning using RL for Harpy (as depicted in Fig. 7), a thruster-assisted bipedal robot developed in collaboration with CalTech. This trajectory planner skillfully navigates obstacles to reach designated goals while minimizing power consumption. I played a pivotal role in guiding the team to frame the trajectory planning problem using RL. Figure 8 illustrates the environmental setup with obstacles within the Webots simulator, used for the initial proof-of-concept implementation.

<div class="row mt-3">
    {% include figure.liquid loading="eager" path="assets/img/harpy.png" class="img-fluid rounded z-depth-1" zoomable=true %}
</div>
<div class="caption">
    Figure 8: Harpy robot
</div>

<div class="row mt-3">
    {% include figure.liquid loading="eager" path="assets/img/harpy_rl.png" class="img-fluid rounded z-depth-1" zoomable=true %}
</div>
<div class="caption">
    Figure 9: Environment setup in webots simulator
</div>

## Thesis Report

Feel free to delve into my comprehensive master's thesis report at [https://doi.org/10.17760/D20659774](https://doi.org/10.17760/D20659774) for an in-depth exploration of model matching and loco-manipulation controller. If your time is limited, you can instead visit my blog post at [https://zer0sh0t.github.io/blog/2024/my-thesis/](https://zer0sh0t.github.io/blog/2024/my-thesis/) for a concise summary of its contents.

## References

[1] "Reinforcement learning-based model matching in COBRA, a slithering snake robot" by Harin Kumar Nallaguntla (2024). [https://doi.org/10.17760/D20659774](https://doi.org/10.17760/D20659774)

[2] [https://www.wired.com/story/rovers-are-so-yesterday-its-time-to-send-a-snakebot-to-space/](https://www.wired.com/story/rovers-are-so-yesterday-its-time-to-send-a-snakebot-to-space/)

[3] [https://www.nasa.gov/directorates/stmd/northeastern-university-slithers-to-the-top-with-big-idea-alternative-rover-concept/](https://www.nasa.gov/directorates/stmd/northeastern-university-slithers-to-the-top-with-big-idea-alternative-rover-concept/)

[4] [https://bigidea.nianet.org/wp-content/uploads/Northeastern-University-2022-Big-Idea-Technical-Paper.pdf](https://bigidea.nianet.org/wp-content/uploads/Northeastern-University-2022-Big-Idea-Technical-Paper.pdf)

[5] "Non-impulsive Contact-Implicit Motion Planning for Morpho-functional Loco-manipulation" by A. Salagame et. al (2024). [https://arxiv.org/abs/2404.08714](https://arxiv.org/abs/2404.08714)

[6] "Loco-Manipulation with Nonimpulsive Contact-Implicit Planning in a Slithering Robot" by A. Salagame et. al (2024). [https://arxiv.org/abs/2404.08174](https://arxiv.org/abs/2404.08174)

[7] "Dynamic Multimodal Locomotion: A Quick Overview of Hardware and Control" by Shreyansh Pitroda (2023). [https://arxiv.org/abs/2310.00008](https://arxiv.org/abs/2310.00008)

[8] "How Strong a Kick Should be to Topple Northeastern's Tumbling Robot?" by A. Salagame et. al (2023). [https://arxiv.org/abs/2311.14878](https://arxiv.org/abs/2311.14878)

[9] [Field testing COBRA at the NASA BIG Idea Forum 2022](https://www.youtube.com/watch?v=Zv2XgsOK-Tg&ab)

[10] [https://www.youtube.com/watch?v=8cmpR3J5gbY&ab](https://www.youtube.com/watch?v=8cmpR3J5gbY&ab)
