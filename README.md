# LLM Mechanics Lab

A personal research notebook for opening up transformer behavior one concrete run at a time.

## Core idea

If we cannot build, inspect, and test a system ourselves, we do not yet fully understand how it works.

This repo is a small lab for doing exactly that with transformer models: tracing how an answer forms, watching competing candidates rise and fall, and then testing causal hypotheses about which internal components actually matter.

## Main artifact

- `notebooks/llm_mechanics_lab.ipynb`

The notebook follows a short in-context capital probe through `gpt2-small` as a guided investigation:

- When does ` Berlin` stop losing to the wrong continuation?
- How do the residual stream and competing tokens change across checkpoints?
- Which residual components push the answer upward?
- Which attention heads matter once we move from description to causal testing?

## What the notebook covers

- residual stream evolution across pre-attention, post-attention, and post-MLP checkpoints
- competing token trajectories across the forward pass
- direct logit attribution
- static attention pattern inspection
- activation patching
- head ablation
- short interpretation blocks after the main figures
- practical implications for debugging, trust, governance, and model-change analysis

## Why this kind of analysis matters once models enter real workflows

Mechanistic inspection helps with more than curiosity:

- narrowing regressions to specific stages or components instead of treating the whole model as a black box
- explaining behavior changes to product, review, and risk stakeholders with stronger evidence than surface examples alone
- checking whether a model update preserved the same internal route or switched to a different and possibly more brittle one
- building a more concrete notion of trust than “it worked on a few prompts”

## Run locally

```powershell
python -m venv .venv
.venv\Scripts\Activate.ps1
pip install -r requirements.txt
jupyter lab
```

Then open `notebooks/llm_mechanics_lab.ipynb`.

## Repo layout

- `notebooks/` holds the main research notebook
- `assets/` is available for exported figures or screenshots when needed
