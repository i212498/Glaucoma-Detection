# Glaucoma Diagnosis with U-Net Architecture

## Introduction

Glaucoma is a chronic eye condition characterized by damage to the optic nerve, often due to increased pressure within the eye. It is one of the leading causes of irreversible blindness worldwide, particularly among the elderly. Early detection and intervention are crucial for preventing vision loss and preserving quality of life.

This project aims to enhance the automated detection and segmentation of key ocular structures relevant to glaucoma diagnosis by leveraging deep learning techniques and semantic segmentation algorithms. The core of this project is the implementation of a U-Net architecture for segmenting optical disks and cups from images, which aids in calculating the Cup-to-Disc Ratio (CDR) to diagnose glaucoma.

## Chosen Deep Learning Architecture

### U-Net

U-Net is selected for its effectiveness in biomedical image segmentation due to its ability to capture both local and global features through a contracting path followed by an expansive path.

#### Network Architecture Details

1. **DoubleConv Module**: 
   - Consists of two consecutive convolutional layers, each followed by batch normalization and ReLU activation. This helps in learning complex patterns from the input image.

2. **UNET Class**:
   - **Upsampling and Downsampling**: Achieved using `nn.MaxPool2d` for downsampling and `nn.ConvTranspose2d` for upsampling.
   - **Bottleneck**: Captures the most abstract features through another DoubleConv operation.
   - **Final Convolution**: Reduces the number of channels to the desired number of output channels (1 for binary segmentation).

## Training Process Details

1. **Data Augmentation**:
   - Techniques include random rotation, horizontal flip, and vertical flip to enhance the model's ability to generalize.
   - Normalization is performed to standardize the input images.

2. **Optimizer**:
   - Adam optimizer with a learning rate of `1e-4`. Known for its adaptive learning rate capabilities.

3. **Learning Rate Schedule**:
   - No explicit learning rate schedule is defined; the learning rate remains constant throughout training.

4. **Loss Function**:
   - Binary Cross-Entropy with Logits Loss (`nn.BCEWithLogitsLoss`), suitable for binary classification tasks like image segmentation.

5. **CDR Calculation**:
   - CDR calculation methods and details are not included in this code snippet but are part of the broader implementation.

## Post-Processing Techniques

Post-processing techniques were not applied in this code snippet. Pre-processing techniques were applied to enhance the quality of input data.

## Usage

To use this project, clone the repository and follow the instructions below:

1. **Clone the Repository**:
   ```bash
   git clone https://github.com/yourusername/your-repository-name.git
   cd your-repository-name
