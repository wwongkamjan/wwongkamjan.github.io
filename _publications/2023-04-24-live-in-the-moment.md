---
title: "Live in the Moment: Learning Dynamics Model Adapted to Evolving Policy"
collection: publications
permalink: /publication/2023-04-24-live-in-the-moment
excerpt: 'Model-based reinforcement learning (RL) often achieves higher sample efficiency in practice than model-free RL by learning a dynamics model to generate samples for policy learning. Previous works learn a dynamics model that fits under the empirical state-action visitation distribution for all historical policies, i.e., the sample replay buffer. However, in this paper, we observe that fitting the dynamics model under the distribution for all historical policies does not necessarily benefit model prediction for the current policy since the policy in use is constantly evolving over time. The evolving policy during training will cause state-action visitation distribution shifts. We theoretically analyze how this distribution shift over historical policies affects the model learning and model rollouts. We then propose a novel dynamics model learning method, named Policy-adapted Dynamics Model Learning (PDML). PDML dynamically adjusts the historical policy mixture distribution to ensure the learned model can continually adapt to the state-action visitation distribution of the evolving policy. Experiments on a range of continuous control environments in MuJoCo show that PDML achieves significant improvement in sample efficiency and higher asymptotic performance combined with the state-of-the-art model-based RL methods.'
date: 2023-04-24
venue: 'Proceedings of the 40th International Conference on Machine Learning'
paperurl: 'https://proceedings.mlr.press/v202/wang23an/wang23an.pdf'
citation: 'Wang, X., Wongkamjan, W., Jia, R. and Huang, F., 2023, July. Live in the moment: Learning dynamics model adapted to evolving policy. In International Conference on Machine Learning (pp. 36470-36493). PMLR.'
---
