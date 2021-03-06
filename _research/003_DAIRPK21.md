---
paper_name: Learning Locomotion Controllers for Walking Using Deep FBSDE
paper_author: Bolun Dai, Virinchi Roy Surabhi, Prashanth Krishnamurthy, Farshad Khorrami
paper_venue: Preprint 2021
paper_link: "https://arxiv.org/abs/2107.07931"
video_link: None
poster_link: None
---
In this paper, we propose a deep forward-backward stochastic differential equation (FBSDE) based control algorithm for locomotion tasks. We also include state constraints in the FBSDE formulation to impose stable walking solutions or other constraints that one may want to consider (e.g., energy). Our approach utilizes a deep neural network (i.e., LSTM) to solve, in general, high-dimensional Hamilton-Jacobi-Bellman (HJB) equation resulting from the stated optimal control problem. As compared to traditional methods, our proposed method provides a  higher computational efficiency in real-time; thus yielding higher frequency implementation of the closed-loop controllers. The efficacy of our approach is shown on a linear inverted pendulum model (LIPM) for walking. Even though we are deploying a simplified model of walking, the methodology is applicable to generalized and complex models for walking and other control/optimization tasks in robotic systems. Simulation studies have been provided to show the effectiveness of the  proposed methodology.