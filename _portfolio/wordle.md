---
title: "Emergent Strategy in Wordle via Reinforcement Learning"
excerpt: "<b>Research Proposal:</b> A theoretical framework and experimental design for inducing expert-level game strategies in LLMs via RL."
collection: portfolio
---

**Advisor:** [Dr. Michael White](https://linguistics.osu.edu/people/white.1240)
**Status:** Proposal & Experimental Design Complete

### Project Overview
This project establishes the theoretical framework for a Reinforcement Learning (RL) agent capable of playing *Wordle*. I have designed an experimental pipeline to test whether a Large Language Model can derive optimal information-theoretic strategies (such as entropy reduction) purely through interaction, without explicit instruction.

### Methodology
* **Agent Architecture:** The design utilizes a Llama-based policy model optimized via Proximal Policy Optimization (PPO).
* **Reward Engineering:** I have formulated a custom reward function that penalizes inefficient guesses to strictly incentivize information maximization.
* **Evaluation Metric:** The proposal includes the design of a "Shannon Entropy Expert" solver to serve as a mathematical upper bound for benchmarking the agent's emergent intelligence.

### Research Hypothesis
I hypothesize that under this specific reward structure, the agent will naturally converge on advanced human-like tactics—specifically **Trap-Set Analysis**—demonstrating that linguistic models can ground reasoning in information-theoretic principles.

### Technical Focus
* **Concepts:** Reinforcement Learning (RL), Information Theory, Experimental Design
* **Tools:** Python, PyTorch (Planned Implementation)