--- 
page-type: blog-post 
title: How to get egocentric global maps in HouseExpo
description: By Bolun Dai | Jan 4th 2021
class: random
link: None
text: Getting egocentric global maps in <cite>HouseExpo</cite>
layout: blog_post
bibliography: 2021-01-04-houseexpo.bib
--- 

HouseExpo<d-cite key="DBLP:conf/iros/LiHLZWM20"></d-cite> is a nice environment for active SLAM research, it provides a simulation environment that enables a robot to move around in a 2D world and drawing maps of the environment. The default output of the simulation a egocentic (the agent centered in the image) local map. A recent work<d-cite key="DBLP:conf/iclr/ChenGG19"></d-cite> provides a nice framework for learning-based exploration tasks. It uses egocentric local maps and global maps as its input to the learning-based controller. To implement an approach like<d-cite key="DBLP:conf/iclr/ChenGG19"></d-cite> on HouseExpo we would need to code it up ourself. This blog is going to talk about how to get a egocentric global map in HouseExpo.

Before we do anything we need to first figure out the coordinate system used in HouseExpo. For any map the origin $$(0, 0)$$ is at the upper left corner. If we use a Cartesian coordinate as comparison, the positive $$x$$-axis in HouseExpo is along the negative $$y$$-axis and the positive $$y$$-axis co-aligns with the positive $$x$$-axis of the Cartesian coordinates. As for the orientation, going from the positive $$x$$-axis in the Cartesian coordinates to the negative $$x$$-axis counterclockwise is going from $$0^\circ$$ to $$180^\circ$$, if going clockwise then it is from $$0^\circ$$ to $$-180^\circ$$ in HouseExpo.

The following can be dissected into two steps: centering the agent and rotating the map. To do this we need to know the size of the background canvas $$(h, w)$$, the position of the agent in the global map $$(p_x, p_y)$$ and the size of the global map $$(g_x, g_y)$$. The we can assign the corresponding cells in the canvas to have equal values as in the global map.

The next step is to rotate the canvas, if the current orientation of the robot is $$+\theta$$, then we would need to rotate the canvas $$-\theta$$. After this we have the rotated image where the robot is heading right, if we want the robot to face up, we would need to rotate the canvas $$90^\circ$$. We use the following image to illustrate this process.

<d-byline></d-byline>

<p class="citation">
    Powered by <a href="https://www.mathjax.org">
    <img title="Powered by MathJax" src="https://www.mathjax.org/badge/mj_logo.png" style="border:0;" alt="Powered by MathJax" />
    </a>
</p>