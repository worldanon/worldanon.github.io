# Supplementary Videos for Learning to Predict Without Looking Ahead: World Models Without Forward Prediction

## Cartpole Swingup

Our agent is given only infrequent observations of its environment, and must learn a world model to fill in the observation gaps. In the environment in the video below, the peek probability is 5%.

<video autoplay muted playsinline loop style="display: block; margin: auto; width: 100%;"><source src="mp4/learncartpole5.mp4" type="video/mp4"/></video>
*Above video corresponds to Figure 1 in the paper*

The world model jointly learned with the policy to fill in the observation gaps in the swingup cartpole environment. The colorless cartpole represents the observation seen by the policy. Solid color cartpole denotes when the agent is allowed to observe the actual environment, and when its internal model is realigned with reality. Light color cartpole denotes actual observations that the agent cannot see.

We can check that the policy that is jointly learned with the world model learns a policy that works when observational dropout is disabled in the environment:

<video autoplay muted playsinline loop style="display: block; margin: auto; width: 100%;"><source src="mp4/controller5.mp4" type="video/mp4"/></video>
*Above: The policy that is jointly learned with the world model, deployed in the original environment where it can see the actual observations at each timestep.*

Section 4.1 of the paper also attempts to train a policy from scratch inside an open loop environment generated by the world model. The below video is the policy learned:

<video autoplay muted playsinline loop style="display: block; margin: auto; width: 100%;"><source src="mp4/dream5.mp4" type="video/mp4"/></video>
*Above: Policy learned inside open loop environment generated by world model trained with peek probability of 5%*

In this world model, the optimal policy learns to swing up the pole and only balance it for a short period of time, even in the self-contained world model.

<video autoplay muted playsinline loop style="display: block; margin: auto; width: 100%;"><source src="mp4/deploy5.mp4" type="video/mp4"/></video>
*Above: Deploying policy learned inside world model (peek probability of 5%) to actual environment*

It should not surprise us then, that the most successful policies when deployed back to the actual environment can swing up and only balance the pole for a short while, before seeing the pole collapse.

We can visualize other open loop environments generated by world models at different peek probabilities. The following corresponds to Figure 3 in the paper:

<video autoplay muted playsinline loop style="display: block; margin: auto; width: 100%;"><source src="mp4/dream10.mp4" type="video/mp4"/></video>
*Above: Policy learned inside open loop environment generated by world model trained with peek probability of 10%*

It is interesting to note that the dynamics in this world model are not perfect. For instance, the optimal policy inside the world model can only swing up and balance the pole at an angle that is not perpendicular to the ground. But surprisingly, when this policy is deployed back into the actual environment, it manages to swing up the pole and balance it for a short period of time:

<video autoplay muted playsinline loop style="display: block; margin: auto; width: 100%;"><source src="mp4/deploy10.mp4" type="video/mp4"/></video>
*Above: Deploying policy learned inside world model (peek probability of 10%) to actual environment*

## Car Racing

Car Racing Section
