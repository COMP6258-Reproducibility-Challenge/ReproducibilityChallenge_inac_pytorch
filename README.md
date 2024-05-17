#Offline Learning
```bash
python run_ac_offline.py --seed 0 --env_name Walker2d --dataset expert --discrete_control 0 --state_dim 17 --action_dim 6 --tau 0.01 --learning_rate 0.0003 --hidden_units 256 --batch_size 256 --timeout 1000 --max_steps 1000000 --log_interval 10000

python run_ac_offline.py --seed 0 --env_name Walker2d --dataset medexp --discrete_control 0 --state_dim 17 --action_dim 6 --tau 0.1 --learning_rate 0.0003 --hidden_units 256 --batch_size 256 --timeout 1000 --max_steps 1000000 --log_interval 10000

python run_ac_offline.py --seed 0 --env_name Walker2d --dataset medium --discrete_control 0 --state_dim 17 --action_dim 6 --tau 0.33 --learning_rate 0.0003 --hidden_units 256 --batch_size 256 --timeout 1000 --max_steps 1000000 --log_interval 10000

python run_ac_offline.py --seed 0 --env_name Walker2d --dataset medrep --discrete_control 0 --state_dim 17 --action_dim 6 --tau 0.5 --learning_rate 0.0003 --hidden_units 256 --batch_size 256 --timeout 1000 --max_steps 1000000 --log_interval 10000
```
#Online Learning

```bash
python run_online_learning.py --seed 0 --env_name Walker2d --dataset expert --discrete_control 0 --state_dim 17 --action_dim 6 --tau 0.01 --learning_rate 0.00001 --hidden_units 256 --batch_size 256 --timeout 1000 --max_steps 1000000 --log_interval 10000

python run_online_learning.py --seed 0 --env_name Walker2d --dataset medexp --discrete_control 0 --state_dim 17 --action_dim 6 --tau 0.1 --learning_rate 0.00001 --hidden_units 256 --batch_size 256 --timeout 1000 --max_steps 1000000 --log_interval 10000

python run_online_learning.py --seed 0 --env_name Walker2d --dataset medium --discrete_control 0 --state_dim 17 --action_dim 6 --tau 0.33 --learning_rate 0.00003 --hidden_units 256 --batch_size 256 --timeout 1000 --max_steps 1000000 --log_interval 10000

python run_online_learning.py --seed 0 --env_name Walker2d --dataset medrep --discrete_control 0 --state_dim 17 --action_dim 6 --tau 0.5 --learning_rate 0.00003 --hidden_units 256 --batch_size 256 --timeout 1000 --max_steps 1000000 --log_interval 10000
```
