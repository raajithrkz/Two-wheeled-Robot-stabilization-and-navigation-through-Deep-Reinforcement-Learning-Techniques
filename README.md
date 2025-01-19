
## Setup & Installation of Repository
The code is written using Python 3.8 and used the following libraries:
```
matplotlib==3.7.1
numpy==1.23.5
opencv_python==4.7.0.72
pandas==2.0.0
pybullet==3.2.5
PyYAML==6.0
seaborn==0.12.2
tensorflow==2.12.0
tensorflow_probability==0.19.0
torch==1.7.1
```

1. Create conda environment
``` 
conda create -n two_wheel_robot python=3.8 
```
2. Activate conda environment
``` 
conda activate two_wheel_robot
```
3. Install Dependencies
``` 
pip install -r requirements.txt 
```


## Folders
### 1. Object Models
This folder stores the two-wheel robot xml file created in Gazebo. The object models for the slope is also stored here. 

### 2. Configs
This folder stores the configuration files (.yaml) for running the training and testing experiments. 

### 3. Results
This folder stores the training and testing results of the model runs and the saved models.


## Training Robot Agent
1. Define your training config file by creating a new config.yaml under configs directory. Rename the run name for every new run so that a new subdirectory will be created under results/train/<run_name> for storing the training plots and model weights.

2. After editing the config file, run the following python code to train the agent.
```
python robot_train.py --config-file ./config/main.yaml
```

## Testing Robot Agent
1. After training a model, find the path tp the saved config file in the results/train/<run_name> directory after training to load the trained model weigths path.

2. Run the following code to test the model
```
python robot_test.py --config-file ./results/train/hyperparam_DQN_slope_40m/epsilon_decay_type_linear/hyperparam_DQN_slope_40m.yaml
```

