---
layout: page
title: Silicon Synapse Lab
description: <p>Research Assistant<br>Apr 2023 - Present<br>Boston, USA</p>
img: assets/img/cobra.png
importance: 1
---

Tools used: Python, MATLAB, Simscape, C/C++, Git, Ubuntu, PyTorch, Gazebo, Webots, ROS

<div class="row mt-3">
    {% include figure.liquid loading="eager" path="assets/img/cobra.png" class="img-fluid rounded z-depth-1" zoomable=true %}
</div>
<div class="caption">
    Figure 1: COBRA robot
</div>

COBRA, short for Crater Observing Bio-inspired Rolling Articulator, is a snake-like robot designed to emulate the movement of serpentine creatures. Engineered to navigate challenging terrains like craters, where traditional robots often struggle, COBRA features 11 joints and 12 links, enabling intricate and versatile movements. With 6 yawing and 5 pitching joints, it offers a wide range of orientations, making it ideal for various robotic applications. Specifically designed to explore hard-to-navigate lunar craters suspected of containing frozen water, COBRA could significantly contribute to identifying these deposits, paving the way for future lunar colonization.

I led the development and maintenance of simulation software for COBRA, an advanced morpho-functional snake robot. Our team successfully secured $1 million in funding from NASA to support lunar surface exploration initiatives and earned top spot at the 2022 NASA BIG Idea Challenge, receiving the prestigious Artemis Award.

<div class="row mt-3">
    {% include video.liquid path="assets/video/sidewinding.mp4" class="img-fluid rounded z-depth-1" controls=true autoplay=false %}
</div>
<div class="caption">
    Video 1: Shows COBRA performing sidewinding motion
</div>

My work primarily focused on bridging the simulation-to-reality gap in the COBRA platform. I developed a reinforcement learning-based framework called "Model Matching," which fine-tunes the simulator model to reduce discrepancies between the real robot and its simulated counterpart in the Webots simulator. By leveraging data from the actual robot, this approach has significantly enhanced the fidelity of the Webots simulator.

As part of the model matching framework, I designed a seamless and intuitive API for the Webots and MuJoCo simulators, enabling effective fine-tuning of simulation parameters using Reinforcement Learning (RL) techniques. I also developed an accelerated RL model training pipeline, resulting in a fourfold increase in training capacity, which substantially expedited the prototyping and deployment processes. This framework has reduced the sim-to-reality gap by over 150%, significantly enhancing the accuracy and fidelity of COBRA’s locomotion simulations.

<div class="row mt-3">
    {% include video.liquid path="assets/video/real_untuned_tuned_text.mp4" class="img-fluid rounded z-depth-1" controls=true autoplay=false %}
</div>
<div class="caption">
    Video 2:  Shows COBRA in Webots simulator with tuned model (right) and untuned model (center) performing the sidewinding motion. The red ball shows the location the actual robot achieved when similar joint trajectories were applied.
</div>

Video 2 demonstrates the final tuned simulator model achieved using the model matching framework. As observed, the tuned simulator model closely matches real-world performance.

<div class="row mt-3">
    <div class="col-sm mt-3 mt-md-0">
        {% include video.liquid path="assets/video/locoman.mp4" class="img-fluid rounded z-depth-1" controls=true autoplay=false %}
    </div>
</div>
<div class="caption">
    Video 3: Shows COBRA performing loco-manipulation
</div>

Additionally, I designed novel RL-guided locomotion patterns tailored for seamless object manipulation, leveraging COBRA’s unique body design to enhance dexterity and precision. Loco-manipulation involves the robot performing locomotion to manipulate objects in its environment, a complex challenge as it requires solving both locomotion and manipulation simultaneously. With the proposed controller, COBRA achieved an impressive success rate of 94.3% in loco-manipulation tasks.

<div class="row mt-3">
    {% include video.liquid path="assets/video/loco_ex4.mp4" class="img-fluid rounded z-depth-1" controls=true autoplay=false %}
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

I led the way in implementing energy-efficient trajectory planning using RL for Harpy (as depicted in Fig. 2), a thruster-assisted bipedal robot developed in collaboration with CalTech. This approach improved performance while emphasizing sustainability. I played a pivotal role in guiding the team to frame the trajectory planning problem using RL. Figure 3 illustrates the environmental setup with obstacles used for the initial implementation of the proposed framework.

<div class="row mt-3">
    {% include figure.liquid loading="eager" path="assets/img/harpy.png" class="img-fluid rounded z-depth-1" zoomable=true %}
</div>
<div class="caption">
    Figure 2: Harpy robot
</div>

<div class="row mt-3">
    {% include figure.liquid loading="eager" path="assets/img/harpy_rl.jpg" class="img-fluid rounded z-depth-1" zoomable=true %}
</div>
<div class="caption">
    Figure 3: Environment setup in webots simulator
</div>

Feel free to delve into my comprehensive master's thesis report at [https://doi.org/10.17760/D20659774](https://doi.org/10.17760/D20659774) for an in-depth exploration of model matching and loco-manipulation controller. If your time is limited, you can instead visit my blog post at [https://zer0sh0t.github.io/blog/2024/my-thesis/](https://zer0sh0t.github.io/blog/2024/my-thesis/) for a concise summary of its contents.

### References

[1] "Reinforcement learning-based model matching in COBRA, a slithering snake robot" by Harin Kumar Nallaguntla (2024). [https://doi.org/10.17760/D20659774](https://doi.org/10.17760/D20659774)

[2] [https://www.wired.com/story/rovers-are-so-yesterday-its-time-to-send-a-snakebot-to-space/](https://www.wired.com/story/rovers-are-so-yesterday-its-time-to-send-a-snakebot-to-space/)

[3] [https://www.nasa.gov/directorates/stmd/northeastern-university-slithers-to-the-top-with-big-idea-alternative-rover-concept/](https://www.nasa.gov/directorates/stmd/northeastern-university-slithers-to-the-top-with-big-idea-alternative-rover-concept/)

[4] [https://bigidea.nianet.org/wp-content/uploads/Northeastern-University-2022-Big-Idea-Technical-Paper.pdf](https://bigidea.nianet.org/wp-content/uploads/Northeastern-University-2022-Big-Idea-Technical-Paper.pdf)

[5] "Non-impulsive Contact-Implicit Motion Planning for Morpho-functional Loco-manipulation" by A. Salagame et. al (2024). [https://arxiv.org/abs/2404.08714](https://arxiv.org/abs/2404.08714)

[6] "Loco-Manipulation with Nonimpulsive Contact-Implicit Planning in a Slithering Robot" by A. Salagame et. al (2024). [https://arxiv.org/abs/2404.08174](https://arxiv.org/abs/2404.08174)

[7] "Dynamic Multimodal Locomotion: A Quick Overview of Hardware and Control" by Shreyansh Pitroda (2023). [https://arxiv.org/abs/2310.00008](https://arxiv.org/abs/2310.00008)
