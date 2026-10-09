# Generative Model Concept Map

This file is a living map of concepts encountered while learning ComfyUI.

The point is not to memorize definitions. Each concept should eventually connect to a workflow experiment.

## Inference

### Prompt

Human-readable instructions.

### Tokenization

Converts text into tokens that a text encoder can process.

### Text encoder

Converts tokenized text into learned vector representations used for conditioning.

In SDXL workflows you will encounter CLIP-family text encoders.

### Conditioning

Information supplied to the generative model that influences what it produces.

Text is one form of conditioning. Later projects will introduce structural, image, depth, pose, and other forms.

### Noise

A stochastic starting signal for diffusion-style generation.

### Seed

A deterministic value used to initialize pseudorandomness. Holding the seed fixed helps controlled experimentation.

### Latent space

A learned compressed representation space where latent-diffusion models perform generation.

### Diffusion / denoising

An iterative generative process that moves a noisy representation toward a structured sample.

### Sampler

The numerical procedure used to traverse the denoising trajectory.

### Scheduler

Controls the sequence/distribution of noise levels used across sampling steps.

### CFG

Classifier-Free Guidance. A mechanism for controlling the strength of conditional guidance during generation.

### VAE

Variational Autoencoder.

Two important directions:

```text
pixels → encoder → latent
latent → decoder → pixels
```

Text-to-image primarily exposes decoding at first.

Img2img will make encoding intuitive.

## Model components

### Checkpoint

A stored collection of trained parameters. Depending on the architecture/package it may expose or bundle several components.

### Diffusion model / denoiser

The learned neural network responsible for predicting information needed to progressively denoise the latent representation.

### LoRA

A parameter-efficient adaptation technique that learns comparatively small low-rank weight updates rather than retraining an entire base model.

### ControlNet

An architecture for supplying additional structural conditioning such as edges, pose, or depth.

## Training concepts — learn later

Do not try to master these before basic inference feels intuitive.

- dataset
- captions
- batch
- epoch
- training step
- loss
- gradient
- backpropagation
- optimizer
- learning rate
- regularization
- validation
- overfitting
- fine-tuning
- LoRA training

## Questions to revisit

1. What exactly is the diffusion model predicting?
2. How does classifier-free guidance work mathematically?
3. Why do different samplers produce different outputs from the same model?
4. What is the mathematical meaning of the noise schedule?
5. What structures emerge in latent representations?
6. How are SDXL, FLUX, and newer generative architectures different?
7. Which parts of the pipeline should a creative agent reason about directly?
