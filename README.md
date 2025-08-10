# Lunar-AI-model

# 🚀 Deep Q-Learning for Lunar Lander

This project implements a **Deep Q-Network (DQN)** to solve the [Lunar Lander](https://gymnasium.farama.org/environments/box2d/lunar_lander/) environment using **PyTorch** and **Gymnasium**.  
It trains an AI agent to land a lunar module safely between two flags by learning an optimal control policy.

## 📌 Features
- **DQN Implementation** with experience replay & target network
- Solves the environment with an average score > 200
- Trains directly in Google Colab
- Video rendering of trained agent performance
- Modular code for reusability and easy tuning of hyperparameters

---

## 📂 Project Structure
```bash
.
├── dqn_lunar_lander.ipynb # Main Colab notebook
├── checkpoint.pth # Saved model weights
├── video.mp4 # Trained agent demo
└── README.md
```

---

## 📦 Installation & Setup

This project is designed to run **directly in Google Colab**.  
If running locally, install the required packages:

```bash
pip install gymnasium
pip install "gymnasium[atari, accept-rom-license]"
apt-get install -y swig
pip install "gymnasium[box2d]"
pip install torch
pip install pygame imageio

```


## Training the Agent


Create the environment:
```bash

import gymnasium as gym
env = gym.make('LunarLander-v3')
Initialize the DQN Agent:
agent = Agent(state_size, action_size)
```
Train:
```bash
for episode in range(1, num_episodes+1):
```
  

Save model when solved:
```bash

torch.save(agent.local_network.state_dict(), 'checkpoint.pth')
```
## 📊 Results
The agent successfully solves the environment in ~800 episodes with an average score > 200.

Training progress:

Episode	Average Score
100	-169.20
500	104.06
800	204.99 ✅

## 🎥 Visualizing the Agent
After training, run:
```bash
show_video_of_model(agent, 'LunarLander-v3')
show_video()
```
A video (video.mp4) will be generated showing the trained agent landing successfully.

## 📚 Learning Resources
- [**Gymnasium Documentation**](https://gymnasium.farama.org/)
- [**PyTorch Documentation**](https://pytorch.org/)
- [**DQN Paper (Mnih et al., 2015)**](https://www.cs.toronto.edu/~vmnih/docs/dqn.pdf)






