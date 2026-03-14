# LLM Mechanics Lab

A personal research project for understanding how transformer language models work under the hood through direct experimentation, visualization, and causal testing.

## Why I built this

I believe that if we cannot build, inspect, and test a system ourselves, then we do not yet fully understand how it works.

This project is my hands-on lab for exploring how internal representations evolve across a transformer, how candidate outputs emerge layer by layer, and how causal interventions can help us identify which components actually matter.

## Main artifact

- `notebooks/llm_mechanics_lab.ipynb`

## What this project explores

- residual stream evolution
- pre-attention vs post-attention vs post-MLP states
- token emergence across checkpoints
- direct logit attribution
- attention pattern inspection
- activation patching
- head ablation

## Project status

Work in progress.