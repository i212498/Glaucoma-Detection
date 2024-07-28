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

#### Implementation
Took a UNET model architecture trained it on our data for segmenting both optic cup and optic disk. Once accuracy was satisfactory, build an application which would take a input feed into both the models, calculate CDR and finally present the resultant image along with the CD Ratio.
