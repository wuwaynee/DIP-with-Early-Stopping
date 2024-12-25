# Generative Models for Visual Signals

## Overview
This project implements a novel method for guiding Deep Image Prior (DIP) early stopping by combining DIP with DDPM-inspired supervision. The approach addresses common challenges in DIP, such as overfitting and unstable image quality during training, by introducing a multi-stage denoising framework.

## Theoretical Justification
- **DIP**: Utilizes a randomly initialized deep convolutional network for image denoising, restoration, and super-resolution.
- **Challenges**: Overfitting noise and difficulty determining the optimal early-stopping point.
- **Proposed Method**:
  1. Generate a series of noise-level images for multi-stage supervision.
  2. Modify DIP training to include multiple denoising stages, starting with high-noise images and progressively reducing noise.
  3. Use metrics like PSNR and SSIM to monitor reconstruction quality and determine early stopping.

## Experimental Setup
1. **Baseline Implementations**:
   - Traditional DIP and DDPM methods.
2. **Dataset**:
   - Smithsonian Butterflies Subset.
3. **Key Configurations**:
   - Three DIP network architectures: U-Net, DnCNN, ResNet.
   - Use of perceptual loss for feature space comparisons.
   - Beta scheduling: Linear and Scaled-Linear schedulers.
   - Two beta_max values: 0.01 and 0.02.

## Results and Observations
- **Performance**:
  - Higher PSNR and SSIM values with the proposed method compared to traditional DIP.
  - U-Net outperforms DnCNN and ResNet.
  - Perceptual loss enhances PSNR and SSIM values.
  - Linear scheduler yields slightly worse results than Scaled-Linear scheduler.
  - Larger beta_max increases complexity and reduces PSNR and SSIM values.
- **Training Efficiency**:
  - No significant increase in time cost compared to traditional DIP.

## Conclusion
The proposed method effectively improves DIP by addressing overfitting and stabilizing image quality through multi-stage denoising. It is a promising approach for future research and development in image restoration techniques.

## How to Run
1. Set up the environment with necessary libraries (e.g., PyTorch, NumPy).
2. Clone the repository and prepare the dataset.
3. Configure training parameters in the script (e.g., network architecture, beta scheduler, loss function).
4. Run the training script and monitor metrics like PSNR and SSIM to evaluate results.

## Future Work
- Explore other datasets and architectures.
- Further optimize the dynamic adjustment mechanism for training epochs.
- Investigate additional loss functions and noise scheduling strategies.
