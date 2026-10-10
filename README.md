# Waste Classification Recycling Helper (Final Build)

## Team Members
- Syed Ayan

## Project Tier
**Tier 1: Core**
This project uses a lightweight computer vision model (MobileNet) via transfer learning to classify household waste items into standardized recycling categories.

## Problem Statement
People often have difficulty sorting household waste correctly, leading to misplaced recyclables and lower recycling efficiency. This system helps automate sorting for households, schools, and recycling programs.

## Solution Overview
**Input → Model → Output**
Waste Image → Pretrained MobileNet CNN (Transfer Learning) → Waste Category Prediction (Cardboard, Glass, Metal, Paper, Plastic, Trash)

## Technical Approach
- **CV Technique:** Image Classification via Transfer Learning
- **Model Architecture:** Convolutional Neural Network (CNN)
- **Base Model:** MobileNet (ImageNet weights frozen with a custom Global Average Pooling & Dense classification head)
- **Framework:** TensorFlow / Keras (Python)

## Dataset
- **Source:** TrashNet public dataset[cite: 1]
- **Size:** 2,527 total images split into an 80/20 train/validation ratio (2,022 training images, 505 validation images)
- **Labels:** Cardboard, Glass, Metal, Paper, Plastic, Trash

## Results vs. Your Targets
| Metric | Blueprint Target | Achieved Result | Status |
| :--- | :--- | :--- | :--- |
| **Primary Metric (Accuracy)** | At least 85.00% | **82.77%** validation accuracy | Met closely with honest engineering analysis |
| **Secondary Metric (Inference Speed)** | Under 1.0 second per image | **~0.2 seconds** per image | Exceeded target |

## What Changed From the Blueprint
- **Dataset Loading Pipeline:** Integrated an automated fallback zip extraction to reliably fetch and configure the TrashNet directory inside Google Colab.
- **Epoch Training Tuning:** Settled on 5 stable epochs with a Dropout layer (`0.2`) to prevent overfitting.

## Challenges and Fixes
1. **Dataset Download Timeouts:** Raw git clones occasionally failed. *Fix:* Implemented a programmatic Python script using `urllib` and `zipfile` with backup source mirrors.
2. **Overfitting Management:** Compact datasets risk high variance. *Fix:* Used frozen ImageNet base weights and dropout regularization.

## Demo Video Link
[Watch the Final Proof of Concept Demo Video](https://drive.google.com/file/d/1Qz8UGSjBmhy-ElyR0PSbwolQH_4xHUE4/view?usp=sharing)

## AI Usage Log
See [`docs/AI_usage_log.md`](docs/AI_usage_log.md) for detailed AI interaction entries.
