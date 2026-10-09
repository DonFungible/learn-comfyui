# Learn ComfyUI

A hands-on curriculum for learning ComfyUI and the generative-model concepts underneath it.

The goal is **not** to collect complicated workflows. The goal is to understand the full image-generation pipeline well enough to eventually build a creative agent that can plan, construct, run, inspect, and iterate on generative workflows.

## Learning philosophy

1. Build workflows manually before importing community graphs.
2. Change one variable at a time.
3. Treat ComfyUI as a visual programming environment, not a magic image generator.
4. Learn what data flows through every wire.
5. Rebuild important workflows in both ComfyUI Cloud and local ComfyUI.
6. Save workflows and experiment results so intuition becomes reproducible knowledge.

## Roadmap

### 01 — Diffusion Microscope
Build the smallest useful SDXL text-to-image workflow from scratch.

Learn:
- checkpoints
- text encoders / CLIP
- conditioning
- noise and seeds
- latent space
- diffusion / denoising
- KSampler
- samplers and schedulers
- CFG
- VAE decoding

### 02 — Image-to-Image Lab
Learn:
- VAE encoding
- denoise strength
- img2img
- masking
- inpainting
- outpainting
- latent compositing

### 03 — Structural Control
Learn:
- ControlNet
- edge conditioning
- depth
- pose
- reference images
- semantic vs structural guidance

### 04 — LoRA Training
Learn:
- datasets
- captions
- batches / epochs / steps
- learning rate
- loss
- gradients and backpropagation
- fine-tuning
- LoRA
- overfitting and validation

### 05 — Modern Generative Architectures
Repeat earlier experiments with newer image/video architectures and compare what changes.

Potential topics:
- FLUX
- modern text encoders
- image editing models
- video diffusion / flow models
- multimodal conditioning

### 06 — Creative Agent
Move from manually operating ComfyUI toward an agent that can reason about creative intent and execute workflows.

Conceptual architecture:

```text
User intent
    ↓
Creative planner / LLM
    ├── model selection
    ├── prompt / conditioning strategy
    ├── workflow selection or construction
    ├── parameter selection
    └── iteration strategy
              ↓
        ComfyUI API / tools
              ↓
         GPU inference
              ↓
           outputs
              ↓
    vision critic / evaluator
              └──────→ iterate
```

## Current project

Start here:

**[01 — Diffusion Microscope](./01-diffusion-microscope/README.md)**

## Core mental model

```text
prompt
  ↓
text encoder
  ↓
conditioning ─────────────┐
                          ↓
random noise → diffusion model + sampler → latent
                                         ↓
                                     VAE decode
                                         ↓
                                       pixels
```

The long-term objective is to understand every arrow in this diagram.

## Repository conventions

Each project should eventually contain:

```text
project/
├── README.md          # lesson + build instructions
├── workflows/         # exported ComfyUI JSON
├── experiments/       # controlled experiments and observations
└── outputs/           # selected generated examples (optional)
```

Do not commit model weights or large generated datasets.
