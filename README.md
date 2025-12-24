# CIFAR-10-Animals
A deep learning project that classifies animals from the CIFAR-10 dataset using Convolutional Neural Networks (CNNs). The project compares two different training configurations to analyze the impact of batch size on model performance.
# Task 3: CIFAR-10 Animals (4 Classes)

**Student:** Nurlan Kangarli  
**ID:** S303  
**Seed:** 20240303

## Presentation
[View Presentation Slides](https://docs.google.com/presentation/d/1mGRNt49waD_L3NI42AMmFFMJzKG5dFY5/edit?usp=drive_link&ouid=113733731367230239482&rtpof=true&sd=true)

## Dataset
- **Name:** CIFAR-10 filtered to 4 animal classes
- **Classes:**  4 (cat, dog, horse, deer)
- **Training samples:** 20 000 
- **Test samples:** 4 000

## Model Architecture
- **Type:**
```
INPUT: 32×32×3 (RGB image)

BLOCK 1:
- Conv2D: 32 filters, kernel_size=3, padding=1, stride=1
- ReLU activation
- MaxPool2D: kernel_size=2, stride=2

BLOCK 2:
- Conv2D: 64 filters, kernel_size=3, padding=1, stride=1
- ReLU activation
- MaxPool2D: kernel_size=2, stride=2

BLOCK 3:
- Conv2D: 128 filters, kernel_size=3, padding=1, stride=1
- ReLU activation
- MaxPool2D: kernel_size=2, stride=2

CLASSIFIER:
- Flatten
- Linear: input_features → 128
- ReLU activation
- Dropout: p=0.5
- Linear: 128 → 4

OUTPUT: 4 classes
```
- **Convolutional layers:** [Number]
- **Fully connected layers:** [Number]
- **Total parameters:** 356,036

## Training Comparison

### Version 1
- **Learning rate:** 0.001
- **Batch size:** 64
- **Optimizer:** Adam
- **Test accuracy:** 86.15%

### Version 2
- **Learning rate:** 0.001
- **Batch size:** 128
- **Optimizer:** Adam
- **Test accuracy:** 85.90%

### Best Result
- **Best version:** Version 1
- **Final test accuracy:** 86.15%
- **Target accuracy:** ≥85%
- **Status:** ✓ Achieved 

## Analysis
- **Best performing class:** automobile  : 93.30% (933/1000)
- **Worst performing class:** bird    : 77.60% (776/1000)
- **Key observations:**
1. Model Optimization: I learned practically how changing batch size (64 vs 128) affects model performance - smaller batch size gives faster convergence, while larger batch size provides more stable results and better generalization.

2. Real-World Analysis: I understood how CNN architecture works to distinguish different animal species (bird, cat, deer, dog) in low-resolution (32×32) real-world images, which is challenging due to small object sizes.

3. Reproducibility: I realized the importance of using fixed random seeds (20240303) for reproducible results in scientific research, ensuring that experiments can be replicated and verified.
## Files
- `notebook.ipynb`: https://github.com/user-attachments/files/24305400/file.ipynb
