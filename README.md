# Supplementary Videos for Learning to Predict Without Looking Ahead: World Models Without Forward Prediction

## Cartpole Swingup

Our agent is given only infrequent observations of its environment, and must learn a world model to fill in the observation gaps. In the environment in the video below, the peek probability is 5%.

<video autoplay muted playsinline loop style="display: block; margin: auto; width: 100%;"><source src="mp4/learncartpole5.mp4" type="video/mp4"/></video>
*Video corresponds to Figure 1 in the paper*

The world model jointly learned with the policy to fill in the observation gaps in the swingup cartpole environment. The colorless cartpole represents the observation seen by the policy. Solid color cartpole denotes when the agent is allowed to observe the actual environment, and when its internal model is realigned with reality. Light color cartpole denotes actual observations that the agent cannot see.

We can check that the controller that is jointly learned with the world model learns a policy that works when observational dropout is disabled in the environment:

<video autoplay muted playsinline loop style="display: block; margin: auto; width: 100%;"><source src="mp4/controller5.mp4" type="video/mp4"/></video>
*The controller that is jointly learned with the world model, deployed in the original environment where it can see the actual observations at each timestep.*


