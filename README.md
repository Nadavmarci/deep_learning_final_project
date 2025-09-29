# Predicting Metasurface Patterns from Light Scattering with Diffusion Models

## Overview
Final project in the Deep Learning M.Sc. course (Tel Aviv University).  
We build a class-conditioned diffusion model (UNet, Hugging Face Diffusers) that predicts the optimal metasurface pattern given its measured light-scattering behavior.

Dataset: 25,000 samples of metasurfaces and their light responses (Nano-Photonics Lab, TAU).  
Best configuration after experiments: 50 epochs, batch size 20, learning rate 3e-4, MSE loss.  
Results (test): accuracy 98.6%, precision 0.995, recall 0.995.

## Data
Each sample includes:
- Pattern: binary 10×10 grid (padded to 32×32, 1 channel).
- Light matrices: transmission (Tm) and reflection (Rm), each 23×23 (padded/normalized to 32×32).
- Height (h): included as an additional channel.

Model inputs:
- Condition: 32×32×3 light “image” (Rm, Tm, h×pattern).
- Target: 32×32×1 pattern image.

## Method
- Class-conditioned diffusion model with a 2D UNet backbone.
- Trained to denoise from y_t to y_0 while conditioned on the light matrix.
- Compared losses (MSE, L1, Huber) and batch sizes (16, 20, 24, 32).
- Addressed failure modes: overfitting (loss choice), high learning rate spikes, normalization issues.

## Results
- Best setting: batch 20, lr 3e-4, MSE loss, ~50 epochs.
- Predicted metasurface patterns match ground truth with high fidelity.
- Additional qualitative examples and training curves are provided in the report.
