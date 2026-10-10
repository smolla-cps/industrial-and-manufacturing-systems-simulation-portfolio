# FlexSim Changeover Times — Reinforcement Learning with PPO

This project integrates a FlexSim simulation model with Python reinforcement learning using Gymnasium and Stable-Baselines3 PPO. FlexSim runs the simulation environment, while Python handles environment interaction, policy training, model saving, testing, and inference.

## Project Components

### FlexSim Model

`ChangeoverTimesRL.fsm` contains the FlexSim simulation and the reinforcement-learning interface used by the Python environment.

The Python environment launches the model in FlexSim training mode and communicates with it through a local TCP socket.

**Integration concepts**
- FlexSim simulation environment
- Reinforcement-learning decision interface
- State/observation exchange
- Action exchange
- Reward exchange
- Episode termination
- Model reset
- Socket-based communication
- Gymnasium-compatible environment

---

### Custom Gymnasium Environment

`flexsim_env.py` defines the `FlexSimEnv` class, which wraps the FlexSim model as a Gymnasium environment.

The environment launches FlexSim, establishes a socket connection, requests the action and observation spaces, sends actions to the simulation, receives observations and rewards, and exposes the standard Gymnasium `reset()` and `step()` interface.

**Main environment functions**
- Launch FlexSim through `subprocess`
- Open a local TCP socket
- Request the FlexSim action space
- Request the FlexSim observation space
- Reset the simulation
- Send RL actions
- Receive state, reward, and termination status
- Convert FlexSim spaces into Gymnasium spaces
- Convert NumPy objects for JSON communication
- Close the FlexSim process

The communication sequence uses messages such as:

```text
ActionSpace?
ObservationSpace?
Reset?
TakeAction:<action>?
```

The environment is configured to communicate with FlexSim through:

```text
localhost:5005
```

---

### PPO Training

`flexsim_training.py` trains a Proximal Policy Optimization policy using Stable-Baselines3.

The script first creates the custom FlexSim Gymnasium environment and checks that it follows the Gymnasium API. It then creates a PPO policy using `MlpPolicy` and trains it on the FlexSim simulation.

**Training configuration**

```text
Algorithm: PPO
Policy: MlpPolicy
Requested training timesteps: 10,000
Environment: FlexSimEnv
```

The trained model is saved as:

```text
ChangeoverTimesModel
```

The training script also runs test episodes after training using actions selected by the trained PPO policy.

---

### Trained PPO Model

`ChangeoverTimesModel.zip` contains the saved Stable-Baselines3 PPO policy.

The saved model metadata shows:

```text
Stable-Baselines3: 2.6.0
Gymnasium: 1.1.1
PyTorch: 2.7.1+cpu
NumPy: 2.3.0
Python: 3.13.4

Observation space: Discrete(5)
Action space: Discrete(5)
PPO rollout steps: 2048
Gamma: 0.99
GAE lambda: 0.95
Batch size: 64
Training epochs per update: 10
Learning rate: 0.0003
```

The training script requests 10,000 timesteps. The saved PPO metadata records 10,240 timesteps because PPO collects complete rollout batches before performing updates.

---

### PPO Inference Server

`flexsim_inference.py` loads the trained PPO model and exposes it through a local HTTP server.

FlexSim or another local process can submit an observation to the server. The server converts the observation to a NumPy array, calls the PPO model's `predict()` method, and returns the selected action as JSON.

The inference server runs at:

```text
http://localhost:8080
```

**Inference workflow**

```text
FlexSim Observation
        ↓
HTTP Request
        ↓
Python Inference Server
        ↓
PPO model.predict()
        ↓
Selected Action
        ↓
JSON Response
        ↓
FlexSim
```

## Reinforcement Learning Workflow

```text
FlexSim Simulation
        ↓
Observation / State
        ↓
FlexSimEnv
        ↓
PPO Policy
        ↓
Action
        ↓
FlexSim Simulation
        ↓
Reward + Next Observation
        ↓
Policy Training
```

During training, the Python process and FlexSim exchange actions and simulation results repeatedly until the episode terminates.

## Recommended Folder Structure

```text
21_FlexSim_Changeover_Times_RL_PPO/
├── README.md
├── requirements.txt
├── ChangeoverTimesRL.fsm
├── flexsim_env.py
├── flexsim_training.py
├── flexsim_inference.py
└── ChangeoverTimesModel.zip
```

## How to Run

### 1. Install the Python Dependencies

```bash
pip install -r requirements.txt
```

### 2. Update the FlexSim Paths

The uploaded Python scripts currently contain Windows paths for FlexSim 2025 and the model file.

Update the following values in `flexsim_env.py` and `flexsim_training.py` if the files are stored in a different location:

```python
flexsimPath = "C:/Program Files/FlexSim 2025/program/flexsim.exe"
modelPath = "C:/path/to/ChangeoverTimesRL.fsm"
```

### 3. Train the PPO Agent

Run:

```bash
python flexsim_training.py
```

The script:
1. Launches FlexSim.
2. Creates the Gymnasium environment.
3. Validates the environment.
4. Trains PPO.
5. Saves the trained model.
6. Runs test episodes.

### 4. Run the Inference Server

Run:

```bash
python flexsim_inference.py
```

The server loads:

```text
ChangeoverTimesModel.zip
```

and waits for observations on:

```text
localhost:8080
```

## Skills Demonstrated

- Discrete-event simulation
- FlexSim
- Reinforcement learning
- Proximal Policy Optimization
- Stable-Baselines3
- Gymnasium
- Custom RL environments
- Simulation-to-Python integration
- Socket communication
- HTTP inference
- State and action-space handling
- Reward-based learning
- Model training
- Model serialization
- Policy inference
- NumPy
- JSON communication
- Python subprocess management

## Notes

- The semantic meaning of the five discrete observations, five discrete actions, and the reward function is defined by the FlexSim model rather than by the Python scripts.
- The Python scripts use local communication, so FlexSim and Python should run on the same machine unless the networking configuration is changed.
- The model paths in the uploaded scripts are machine-specific and should be edited before running the project on another computer.
- The saved PPO model was trained on CPU.
