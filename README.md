# 🤖 Autonomous Navigation Agent (Unity ML-Agents)

**📅 Project Date:** 2021
**🛠️ Tech Stack:** Unity 3D, C#, Python, PyTorch, ML-Agents
**🧠 Algorithm:** Proximal Policy Optimization (PPO)

### 📖 Project Overview
This project explores **Deep Reinforcement Learning (DRL)** by training autonomous agents to navigate complex 3D environments. Using the **Unity ML-Agents Toolkit**, I developed a "Hallway Navigation" simulation where agents learn spatial awareness and goal recognition without hard-coded pathfinding logic.

The goal was to demonstrate **Sim-to-Real** transfer potential, where policies trained in high-fidelity simulations can be deployed to physical robots for navigation tasks in hazardous terrains.

### 🏗️ System Architecture
The system uses a Python-Unity bridge to train Neural Networks. The agent observes the environment via Raycasts and Vector Observations, processes them through a PyTorch model, and executes discrete actions.

![Architecture](./screenshots/learning_environment_full.png)

### 🧩 Implementation Details
* **Agent Logic:** Custom `HallwayAgent` class inheriting from `Agent`. Handles sensor data collection and reward signals.
* **Reward Function:**
    * `+1.0`: Reaching the correct target ('O' or 'X').
    * `-0.1`: Wall collisions (encouraging safety).
    * `-1/MaxStep`: Time penalty (encouraging efficiency).
* **Algorithm (PPO):** Utilized Proximal Policy Optimization to stabilize training. The objective function maximizes expected return while constraining policy updates:

![PPO Formula](./screenshots/formula.PNG)

### 📸 Simulation & Results
**Training Performance (TensorBoard):**
The agent successfully converged, showing increased cumulative reward and decreased entropy over 50k steps.

| Agent Environment | Training Metrics |
| :---: | :---: |
| ![Hallway](./screenshots/hallway.jpg) | ![TensorBoard](./screenshots/mlagents-TensorBoard.png) |

### 🛠️ Class Structure
The codebase follows a modular structure decoupling Agent logic from Environment settings.
*(See `HallwayAgent` Class Diagram below)*

![Class Diagram](./screenshots/class2.PNG)

### 📄 Documentation
The full research documentation, including detailed mathematical foundations and experimental setup, is available here:
[View Project Documentation](./Major%20Project%20Documentaion.pdf)
