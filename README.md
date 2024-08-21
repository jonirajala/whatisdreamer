# Dreamer
Learning what is the dreamer RL model

## Sources:
### Dreamer model according to chatGPT:

The Dreamer model is a type of reinforcement learning (RL) algorithm designed to handle complex tasks by learning world models, which enable it to predict future states and plan actions effectively.

1. World Model:

    The Dreamer model learns an internal representation of the environment, known as the world model. This model predicts future states and rewards based on the agent's current state and actions. The idea is that instead of relying purely on real-world interactions (which can be expensive or slow), the agent can simulate future scenarios internally, or "dream," to plan its actions.

2. Latent space

    Dreamer operates in a latent space, meaning it encodes observations into a lower-dimensional representation. This makes the learning process more efficient because it reduces the complexity of the environment the agent has to deal with.

3. Imagination

    Once the world model is trained, the Dreamer model can "imagine" future trajectories by predicting sequences of future states and rewards in its latent space. This allows the agent to evaluate potential future outcomes without needing to interact with the actual environment.

4. Planning:

    Based on its imagined trajectories, Dreamer plans and selects actions that maximize the expected cumulative reward. This planning is done over a finite horizon, meaning the agent considers a sequence of actions rather than a single one, to optimize long-term outcomes.

### Dreamer v1 - DREAM TO CONTROL: LEARNING BEHAVIORS BY LATENT IMAGINATION 2020
https://arxiv.org/pdf/1912.01603

- Compared to predictions in image space, latent states have a small memory footprint that enables imagining thousands of trajectories in parallel.
- We present Dreamer, an agent that learns long-horizon behaviors from images purely by latent imagination.
- A novel actor critic algorithm accounts for rewards beyond the imagination horizon while making efficient use of the neural network dynamics. For this, we predict state values and actions in the learned latent space
- In comparison to actor critic algorithms that learn online or by experience replay (Lillicrap et al., 2015; Mnih et al., 2016; Schulman et al., 2017; Haarnoja et al., 2018; Lee et al., 2019), world models can interpolate past experience and offer analytic gradients of multi-step returns for efficient policy optimization.
-  Dreamer uses a latent dynamics model that consists of three components. The
representation model encodes observations and actions to create continuous vector-valued model states st with Markovian transitions (Watter et al., 2015; Zhang et al., 2019; Hafner et al., 2018). The transition model predicts future model states without seeing the corresponding observations that will later cause them. The reward model predicts the rewards given the model states
-Action and value models Consider imagined trajectories with a finite horizon H. Dreamer uses an actor critic approach to learn behaviors that consider rewards beyond the horizon. We learn an action model and a value model in the latent space of the world model for this. The action model implements the policy and aims to predict actions that solve the imagination environment. The value model estimates the expected imagined rewards that the action model achieves from each state sτ

### Dreamer v2 - MASTERING ATARI WITH DISCRETE WORLD MODELS 2021
https://arxiv.org/pdf/2010.02193

- In this paper, we introduce DreamerV2, the first reinforcement learning agent that achieves humanlevel performance on the Atari benchmark
- To achieve this, we apply small modifications to the Dreamer agent (Hafner et al., 2019), such as using discrete latents and balancing terms within the KL loss
- DreamerV1, by replacing its Gaussian latents with categorical variables.

### Dreamer v3 - Mastering Diverse Domains through World Models 2023
https://arxiv.org/pdf/2301.04104

- Applied out of the box, Dreamer v3 is the first algorithm to collect diamonds in Minecraft from scratch without human data or curricula


### Intresting other papers
- DriveDreamer: Towards Real-world-driven World Models for Autonomous Driving
    - https://arxiv.org/pdf/2309.09777