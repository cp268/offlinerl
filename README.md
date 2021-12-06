# Building a pipeline for offline reinforcement learning

The purpose of this repository is to build a pipeline for offline reinforcement learning.

# Getting Started

This project is customized to training CQL on a custom dataset in d3rlpy and training OPE (FQE) to evaluate the trained policy. The starter code has been forked from [d3rlpy](https://github.com/takuseno/d3rlpy) (_see citation at the bottom_). The 'cql_train.py' is the key script used to train the cql and generate the evaluation scores.

### More info on d3rlpy
> d3rlpy is an offline deep reinforcement learning library for practitioners and researchers.
- Documentation: https://d3rlpy.readthedocs.io
- Paper: https://arxiv.org/abs/2111.03788

d3rlpy is benchmarked to ensure the implementation quality. The benchmark scripts are available in the reproductions directory and the results are avaialble in the d3rlpy-benchmarks repository. 

Some examples using d3rlpy include:
  * **MuJoCo** (See more datasets at [d4rl](https://github.com/rail-berkeley/d4rl))
  * **Atari2600** (See more Atari datasets at [d4rl-atari](https://github.com/takuseno/d4rl-atari))
  * **PyBullet** (See more PyBullet datasets at [d4rl-pybullet](https://github.com/takuseno/d4rl-pybullet))

### Installation

---
1. Clone this repository: `git clone https://github.com/cp268/offlinerl`
2. Install **pybullet** from source: `pip install git+https://github.com/takuseno/d4rl-pybullet`
3. Install requirements: `pip install Cython numpy` & `pip install -e`
4. Execute **`cql_train.py`** found at the root of the project
   * Default dataset is `hopper-bullet-mixed-v0` 
   * For example if we want to run for 30 epochs: `python cql_train.py --epochs_cql 30 --epochs_fqe 30` 
   (see colab example below)
5. **Key Logs:**
   * Estimated Q values vs training steps: `d3rlpy_logs/CQL_hopper-bullet-mixed-v0_1/init_value.csv`
   * Average reward vs training steps: `d3rlpy_logs/CQL_hopper-bullet-mixed-v0_1/environment.csv`
   * True Q values vs training steps: `d3rlpy_logs/CQL_hopper-bullet-mixed-v0_1/true_q_value.csv`
   * Note: logs can be found in '/d3rlpy_logs'

### Google Colab Example: [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/drive/1aegKgPZkzLtCDcAnKdkLj5j1MKJgxdvS?usp=sharing)
---

## Useful tutorial
Try a cartpole example on Google Colaboratory:
 * official offline RL tutorial: [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/takuseno/d3rlpy/blob/master/tutorials/cartpole.ipynb)

## Citation
> https://github.com/takuseno/d3rlpy.git 

The paper is available [here](https://arxiv.org/abs/2111.03788).
```
@InProceedings{seno2021d3rlpy,
  author = {Takuma Seno, Michita Imai},
  title = {d3rlpy: An Offline Deep Reinforcement Library},
  booktitle = {NeurIPS 2021 Offline Reinforcement Learning Workshop},
  month = {December},
  year = {2021}
}
```
