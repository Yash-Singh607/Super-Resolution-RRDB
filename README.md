# Image Super-Resolution using RRDBNet

## Overview
This project implements a deep learning-based Single Image Super-Resolution (SISR) model using the Residual-in-Residual Dense Block Network (RRDBNet) architecture inspired by ESRGAN. The objective is to reconstruct high-resolution (HR) images from low-resolution (LR) inputs while preserving fine textures and sharp details.

---

## Problem Statement
Low-resolution images often suffer from:
- Loss of high-frequency details  
- Blurred edges  
- Reduced perceptual clarity  

Traditional interpolation techniques such as bilinear and bicubic upsampling fail to restore fine textures effectively. This project learns a direct mapping:

LR → HR

using a deep convolutional neural network.

---

## Model Architecture
The model is based on RRDBNet and includes:
- Initial feature extraction layer  
- Multiple Residual-in-Residual Dense Blocks (RRDB)  
- Dense skip connections for improved gradient flow  
- Residual learning without Batch Normalization  
- PixelShuffle upsampling layers  
- Final reconstruction layer  

This design enables stable training and high-quality texture reconstruction.

---

## Technical Details
- Upscaling Factor: ×4  
- Framework: PyTorch  
- Loss Function: L1 Loss  
- Optimizer: Adam  
- Training Type: Supervised learning on paired LR-HR images  

---

## Project Structure

Super_Resolution/
│
├── train.py  
├── test.py  
├── model.py  
├── dataset.py  
├── RRDBNet_arch.py  
├── app.py  
├── requirements.txt  
├── README.md  
└── .gitignore  

---

## Dataset
The model is trained using paired datasets containing:
- LR (Low Resolution) images  
- HR (High Resolution) images  

Public datasets such as DIV2K or any custom paired dataset can be used.

Dataset structure:

dataset/
├── LR/  
└── HR/  

---

## Installation

pip install -r requirements.txt

---

## Training

python train.py

Training will load LR-HR image pairs, optimize reconstruction loss, and save model checkpoints in the `models/` directory.

---

## Testing

python test.py

This will load trained weights, generate super-resolved images, and save outputs in the `results/` directory.

---

## Evaluation Metrics
- PSNR (Peak Signal-to-Noise Ratio)  
- SSIM (Structural Similarity Index)  
- Visual comparison with ground truth  

---

## Applications
- Medical image enhancement  
- Satellite imagery refinement  
- Surveillance footage improvement  
- Image restoration  
- Video frame upscaling  

---

## Technologies Used
- Python  
- PyTorch  
- NumPy  
- OpenCV  
- Matplotlib  

---

## Future Improvements
- Integrate adversarial training 
- Add perceptual loss  
- Automate PSNR/SSIM evaluation  
- Deploy as a web application  
- Optimize for real-time inference  

---

## Author
Yash Pratap Singh  

---

## License
This project is intended for academic and research purposes.