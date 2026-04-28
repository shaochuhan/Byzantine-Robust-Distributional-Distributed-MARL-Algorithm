# Byzantine-Robust Distributional Distributed MARL (BRD²MARL / BRD²AC)

This repository contains the official PyTorch implementation of **Byzantine-Robust Distributional Distributed Multi-Agent Reinforcement Learning Algorithm (BRD²MARL / BRD²AC)**, a robust MARL method designed for **continuous control tasks** under communication constraints and malicious Byzantine attacks.

## Key Features
- **Byzantine Attack Resistance**: Defends against various malicious agent attacks in fully distributed MARL systems
- **Asymmetric Robust Consensus**: Heavy-duty nonlinear filtering for Critic, lightweight trust-region for Actor
- **Distributional Value Learning**: Models return distribution for noise-robust and stable training
- **Wasserstein Policy Optimization**: Zero-sampling-variance gradient for reliable policy update
- **Fully Decentralized**: No centralized controller, only neighbor-to-neighbor communication
- **Theoretical Convergence Guarantees** under Byzantine attacks

## Framework Diagram
![BRD²MARL Framework](https://github.com/shaochuhan/Byzantine-Robust-Distributional-Distributed-MARL-Algorithm/raw/main/framework.png)

## Project Structure
```text
Distributional-Distributed-MARL-Algorithm/
├── agents/         # Core agent and trainer implementations
├── config/         # Configuration files for all environments
├── envs/           # CACC, VMAS, and networked control environments
├── utils.py        # Consensus, attack, and utility functions
├── main.py         # Training, evaluation, and attack entry
└── requirements.txt # Dependencies
```

## Getting Started
### Train
```bash
python main.py --base-dir ./exp/d2marl train --config-dir ./config
python3 main.py evaluate --config-dir ./config/brd2marl --version v1 --malicious-agents 1 --malicious-type opposite
```
### Evaluate
```bash
python3 main.py evaluate --config-dir ./config/brd2marl --version v1 --malicious-agents 1 --malicious-type opposite --evaluation-seeds 100
```
## Supported Byzantine Attack Types
- Sign-flipping Attack
- Opposite Attack
- Random Attack

## Supported Environments
- Cooperative Adaptive Cruise Control (CACC)
- Vectorized Multi-Agent Simulator (VMAS)
- Networked System Control with Byzantine Agents
