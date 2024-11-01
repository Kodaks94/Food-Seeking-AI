# Advanced Memory Models for Control in Recurrent Neural Networks

This repository implements and compares advanced memory models within Recurrent Neural Networks (RNNs) for control tasks in partially observable environments (POEs). Key models tested include Long Short-Term Memory (LSTM), Context-Adaptive RNN Unit (CARU), Minimal Gated Unit (MGU), and a modified recurrent network without gating, termed “Identity.” These models were evaluated on a dynamic control task to assess their effectiveness in reinforcement learning scenarios.

## Overview

This project builds on foundational RNN memory research, exploring how different memory architectures can improve control tasks that require efficient and adaptive memory handling. Each model was trained using Backpropagation Through Time (BPTT) on the **EnvironmentAntfood** task, where agents navigate and learn based on past experiences in dynamic environments.

### Memory Models Analyzed

1. **Jordan Recurrent Network & Identity Model**  
   A simplified architecture without gating mechanisms. The Identity model serves as a baseline for examining minimal memory structures in control tasks.
   
2. **Long Short-Term Memory (LSTM)**  
   LSTM includes gating mechanisms (input, forget, output gates) that support long-term memory retention, making it ideal for complex tasks with extended dependencies.
   
3. **Context-Adaptive RNN Unit (CARU)**  
   CARU dynamically adjusts attention to inputs based on task relevance, enhancing adaptability in environments where input significance fluctuates.
   
4. **Minimal Gated Unit (MGU)**  
   A streamlined memory model with a single gate for simpler, efficient memory management without sacrificing performance.

### Model Integration in Control Tasks

Each memory model was trained on a partially observable environment using BPTT. Models were integrated into the physics of the control task, managing memory states based on environmental feedback. By testing memory models in scenarios requiring adaptive navigation and goal-reaching, this project provides insights into the role of memory structures in reinforcement learning.

## Experiment Setup

To ensure fair comparisons, identical hyperparameters and environmental conditions were applied across all models. Performance was measured on the **EnvironmentAntfood** task, where agents with different memory structures were tested on their ability to navigate to randomly placed goals.

### Evaluation Metrics

- **Average Reward at 10,000 Iterations**  
   - Performance was measured over 20 trials for each model, with rewards recorded at set intervals to compare learning progress and adaptability.

- **Path Visualization**  
   - Paths taken by agents with each memory model were visualized to demonstrate strategy adaptations in navigating dynamic environments.

## Results

![Performance Comparison](results.pdf)

**Key Findings:**

1. **Full-LSTM** demonstrated the highest average reward, effectively retaining information over long-term dependencies.
2. **MGU** performed competitively, offering a simpler, computationally efficient alternative to LSTM.
3. **CARU** provided context-sensitive adaptability, beneficial for tasks with shifting input relevance.
4. **Identity Model** showed instability due to the absence of gating, highlighting the importance of structured memory management.

| Memory Model    | Avg. Reward at 10,000 Iterations |
|-----------------|----------------------------------|
| Full-LSTM       | 23.88                            |
| MGU             | 22.74                            |
| CARU            | 19.56                            |
| Identity        | 17.35                            |
| No Memory       | 10.76                            |

## Discussion

The results emphasize the importance of advanced memory models in reinforcement learning for control tasks. While simple architectures (e.g., Identity) provide baseline functionality, models with sophisticated memory structures (e.g., Full-LSTM, MGU) demonstrate enhanced adaptability, efficiency, and decision-making capability in dynamic environments.

### Implications for Reinforcement Learning

This work shows that memory-integrated RNNs outperform non-memory-based networks in tasks requiring environmental recall and adaptability. The **Full-LSTM** and **MGU** models, in particular, highlight how memory aids in strategic planning and accelerates learning. Future research may focus on refining and testing memory models in more complex environments.

## Conclusion

Integrating memory models within RNNs presents significant advantages for control tasks in partially observable environments. Advanced memory architectures such as LSTM and CARU improve adaptability and reward efficiency, while simpler models like Identity illustrate foundational memory integration. This project contributes to understanding the role of memory in RNN-based control, with implications for developing more robust reinforcement learning systems.

