# COMP6258 Reproducibility Challenge
## The In-Sample Softmax for Offline Reinforcement Learning
For the COMP6258 University module we reproduce all key parts of the paper the ICLR 2023 notable top 25\% paper: `The In-Sample Softmax for Offline Reinforcement Learning'. We recreate the tabular environment and reproduce the performance graphs on the Mujoco environment by training the agent offline and then fine-tuning using online learning, concluding that this paper is largely reproducible with minor inconsistencies between their updated graph and the performance tables. Within this GitHub repository we include the code implemeted ourselves to reproduce the Tabular environment and fine-tuning online learning. The Tabular environment is self contained with unit tests, whereas, the online learning files are integrated into the original code.

# Usage for each Section
## Tabular Environment
```bash
python complete_run.py --dataset expert

python complete_run.py --dataset missing1

python complete_run.py --dataset missing2

python complete_run.py --dataset random

python complete_run.py --dataset mixed
```
## Offline Learning

```bash
python run_ac_offline.py --seed 0 --env_name Walker2d --dataset expert --discrete_control 0 --state_dim 17 --action_dim 6 --tau 0.01 --learning_rate 0.0003 --hidden_units 256 --batch_size 256 --timeout 1000 --max_steps 1000000 --log_interval 10000

python run_ac_offline.py --seed 0 --env_name Walker2d --dataset medexp --discrete_control 0 --state_dim 17 --action_dim 6 --tau 0.1 --learning_rate 0.0003 --hidden_units 256 --batch_size 256 --timeout 1000 --max_steps 1000000 --log_interval 10000

python run_ac_offline.py --seed 0 --env_name Walker2d --dataset medium --discrete_control 0 --state_dim 17 --action_dim 6 --tau 0.33 --learning_rate 0.0003 --hidden_units 256 --batch_size 256 --timeout 1000 --max_steps 1000000 --log_interval 10000

python run_ac_offline.py --seed 0 --env_name Walker2d --dataset medrep --discrete_control 0 --state_dim 17 --action_dim 6 --tau 0.5 --learning_rate 0.0003 --hidden_units 256 --batch_size 256 --timeout 1000 --max_steps 1000000 --log_interval 10000
```
## Online Learning

```bash
python run_online_learning.py --seed 0 --env_name Walker2d --dataset expert --discrete_control 0 --state_dim 17 --action_dim 6 --tau 0.01 --learning_rate 0.00001 --hidden_units 256 --batch_size 256 --timeout 1000 --max_steps 1000000 --log_interval 10000

python run_online_learning.py --seed 0 --env_name Walker2d --dataset medexp --discrete_control 0 --state_dim 17 --action_dim 6 --tau 0.1 --learning_rate 0.00001 --hidden_units 256 --batch_size 256 --timeout 1000 --max_steps 1000000 --log_interval 10000

python run_online_learning.py --seed 0 --env_name Walker2d --dataset medium --discrete_control 0 --state_dim 17 --action_dim 6 --tau 0.33 --learning_rate 0.00003 --hidden_units 256 --batch_size 256 --timeout 1000 --max_steps 1000000 --log_interval 10000

python run_online_learning.py --seed 0 --env_name Walker2d --dataset medrep --discrete_control 0 --state_dim 17 --action_dim 6 --tau 0.5 --learning_rate 0.00003 --hidden_units 256 --batch_size 256 --timeout 1000 --max_steps 1000000 --log_interval 10000
```

# D4RL installation
## Paper's Installations
If you are using *Ubuntu* and have not got *d4rl* installed yet, this section may help

1. Download mujoco

	I am using mujoco210. It can be downloaded from https://github.com/deepmind/mujoco/releases/download/2.1.0/mujoco210-linux-x86_64.tar.gz
   ```
   mkdir .mujoco
   mv mujoco210-linux-x86_64.tar.gz .mujoco
   cd .mujoco
   tar -xvzf mujoco210-linux-x86_64.tar.gz
   ```

    Then, add mujoco path:

	Open .bashrc file and add the following line:
	```
    export LD_LIBRARY_PATH=$LD_LIBRARY_PATH:<Your_path>/.mujoco/mujoco210/bin
    ```

	Save the change and run the following command:
	```
    source .bashrc
    ```
	
2. Install other packages and D4RL
    ```
    pip install mujoco_py
    pip install dm_control==1.0.7
    pip install git+https://github.com/Farama-Foundation/d4rl@master#egg=d4rl
    ```
	
3. Test the installation in python
    ```
       import gym
       import d4rl
       env = gym.make('maze2d-umaze-v1')
       env.get_dataset()	   
   ```
