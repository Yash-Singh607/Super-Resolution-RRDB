📸 Image Super-Resolution using RRDBNet
🔎 Overview

This project presents a deep learning-based Single Image Super-Resolution (SISR) system built using the Residual-in-Residual Dense Block Network (RRDBNet) architecture, inspired by the design introduced in ESRGAN by Xintao Wang.

The objective is to reconstruct high-resolution (HR) images from low-resolution (LR) inputs while preserving fine textures, sharp edges, and structural consistency.

🎯 Problem Statement

Low-resolution images commonly suffer from:

Loss of high-frequency details
Blurred edges
Reduced perceptual sharpness
Texture distortion

Traditional interpolation methods such as bilinear and bicubic upsampling are incapable of reconstructing lost details.

This project learns a nonlinear mapping:

LR Image → Deep Feature Extraction → HR Reconstruction
using a deep convolutional neural network trained on paired LR–HR datasets.

🧠 Model Architecture

The model is based on the RRDBNet architecture and includes:

Initial convolutional feature extraction layer
Multiple Residual-in-Residual Dense Blocks (RRDBs)
Dense skip connections for improved gradient propagation
Residual learning without Batch Normalization (to reduce artifacts)
PixelShuffle upsampling layers for efficient resolution scaling
Final reconstruction layer

This architecture enables:

Stable deep network training
Improved texture fidelity
Enhanced structural detail preservation
Better perceptual quality

⚙️ Technical Specifications

Component	Configuration
Upscaling Factor	×4
Framework	PyTorch
Loss Function	L1 Loss
Optimizer	Adam
Training Type	Supervised (paired LR–HR images)
Evaluation Metrics	PSNR, SSIM

📂 Project Structure

Super_Resolution/
│
├── train.py                # Training pipeline
├── test.py                 # Inference script
├── model.py                # Model wrapper
├── dataset.py              # Dataset loader
├── RRDBNet_arch.py         # RRDBNet architecture definition
├── app.py                  # Web interface (optional)
├── requirements.txt        # Dependencies
├── README.md
└── .gitignore

📊 Dataset

The model is trained using paired datasets containing:

LR (Low Resolution) images
HR (High Resolution) images

Public datasets such as:
DIV2K
can be used, or any custom paired dataset.

Expected Dataset Structure
dataset/
├── LR/
└── HR/

🛠️ Installation
pip install -r requirements.txt

🏋️ Training

python train.py

During training:

LR–HR image pairs are loaded
Reconstruction loss is minimized
Model checkpoints are saved in the models/ directory

🖼️ Testing / Inference

python test.py

The script will:

Load trained model weights
Generate super-resolved images
Save outputs in the results/ directory

📈 Evaluation Metrics

Model performance is evaluated using:
PSNR (Peak Signal-to-Noise Ratio)
SSIM (Structural Similarity Index)
Qualitative visual comparison with ground truth

🧰 Technologies Used

Python
PyTorch
NumPy
OpenCV
Matplotlib

🔮 Future Improvements

Integrate adversarial training (GAN-based enhancement)
Add perceptual (VGG-based) loss
Automate PSNR/SSIM evaluation pipeline
Deploy via web application interface
Optimize for real-time and edge inference
Convert to ONNX / TensorRT for deployment

👨‍💻 Author

Yash Pratap Singh
Deep Learning & Computer Vision Enthusiast

📜 License

This project is intended for academic and research purposes.