# Microgrid RL Comparison Notebook  
**By PhD Candidate – Gururaj H. C.**

📂 **Filename:** `Microgrid_Environment_Comparison_Notebook.py`  
🔗 **Repository:** [Reinforcement Learning for Sustainable Energy](https://github.com/Gururaj008/Reinforcement_Learning_for_Sustainable_Energy)

---

## 📌 Overview

This notebook compares the performance of a baseline **random policy** against a trained **Deep Q-Network (DQN)** agent for battery dispatch control in a microgrid environment. The system simulates energy flow over a **24-hour horizon**, using real weather data from the **MERRA-2 dataset**.

---

## ⚙️ Key Components

### 1. Data Handling
- Loads 20 years of irradiance (IR) and wind speed (WS) data from Excel.
- Resamples and normalizes to generate realistic hourly solar/wind input.

### 2. Environment
- `MicrogridEnvBaseline` is an OpenAI Gym-compatible environment.
- **Observation Space:** `[SOC, solar_gen, wind_gen, load, hour_of_day]` (normalized).
- **Actions:** `{0: discharge, 1: hold, 2: charge}`.
- Tracks state of charge (SOC), grid import/export, and computes rewards based on:
  \[
  \text{Reward} = -\text{Import Cost} + \text{Export Revenue} - 0.01 \times \text{Unmet Demand}
  \]

### 3. Reinforcement Learning Agent
- Implements a DQN with:
  - 2 hidden layers of 24 ReLU units each
  - Experience replay
  - Target network updates
  - Decaying ε-greedy exploration strategy
- Trained over 100 episodes with batch size of 24.

### 4. Evaluation Routine
- Runs both random and DQN policies on the **same weather slice**.
- Logs key metrics: SOC, reward, grid import/export.

### 5. Visualization
Generates plots for direct comparison:
- 📈 **Reward vs. Time**
- 🔋 **SOC vs. Time**
- ⚡ **Net Grid Import/Export vs. Time**

---

## 🎯 Purpose & Outcome

This project illustrates the practical use of **deep reinforcement learning for energy management**. Key outcomes:

- 🔹 Reduced grid dependency
- 🔹 Optimized energy usage and cost
- 🔹 Increased system self-sufficiency

The results validate both the environment dynamics and the effectiveness of learning-based control strategies in sustainable microgrid systems.

---

## 📬 Contact

If you'd like to collaborate, discuss the results, or request a live demo:

**Gururaj H. C.**  
📧 gururaj008@gmail.com  
📞 +91 98865 61594  
🌐 [LinkedIn](https://www.linkedin.com/in/gururaj-hc-data-science-enthusiast/)

---

