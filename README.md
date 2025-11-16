# RMCSNet: Road-aware Multi-scale Context and Spatial Attention Network for Remote Sensing Road Extraction

**RMCSNet** is a hybrid CNN–Transformer architecture designed for **accurate and topologically consistent road network extraction** from high-resolution remote sensing imagery. It addresses two fundamental challenges in remote sensing road segmentation:  
🔹 **Fragmentation of long-spanning or narrow roads** due to limited receptive fields  
🔹 **Missed or blurred road segments under occlusion** (e.g., by buildings or vegetation)

To tackle these issues, RMCSNet introduces three key components:
- **Parallel Attention Module (PAM)**: Preserves fine road details by fusing multi-scale features with channel-only attention.
- **Context-Aware Multi-Scale Fusion (CAMF)**: Captures long-range road connectivity via multi-window Swin Transformer blocks.
- **Multi-Scale Decoder (MSD)**: Refines hierarchical features to recover precise road boundaries.

---

## 🏗️ Model Architecture

RMCSNet is built upon a ResNet-34 encoder and a custom decoder, enhanced with three novel modules:
![Model Architecture](fig/1.pdf)

### 1. Parallel Attention Module (PAM)
- Integrated into skip connections to mitigate detail loss during downsampling.
- Uses parallel branches with patch-aware convolutions and **ECA (Efficient Channel Attention)** to enhance road-relevant features while suppressing background noise.
![PAM Architecture](fig/2.pdf)

### 2. Context-Aware Multi-Scale Fusion (CAMF)
- Deployed at the bottleneck of the encoder–decoder.
- Leverages **multi-window Swin Transformer blocks** (window sizes: 2×2, 4×4, 8×8, 16×16) to model global road context.
- Fuses multi-scale features with global attention gating for coherent road structure recovery.
- ![PAM Architecture](fig/3.pdf)

### 3. Multi-Scale Decoder (MSD)
- Progressively upsamples and refines features from multiple encoder stages.
- Ensures high-resolution output with sharp road boundaries.
- ![PAM Architecture](fig/4.pdf)

*(Architecture diagram will be included upon paper publication.)*

---

## 📊 Experimental Results

![Experiment1](fig/5.pdf)
![Experiment2](fig/6.pdf)

---

## 🧪 Requirements

- Python ≥ 3.9  
- PyTorch 2.1.2  
- CUDA 11.8 or higher  
- Dependencies: `torchvision`, `numpy`, `opencv-python`, `scikit-learn`

---

## ▶️ Training & Evaluation

The training and inference code for RMCSNet will be released **after the official publication of the paper**.  
🔔 Please star this repository and check back for updates!

---

## 📄 Citation

If you find RMCSNet useful in your research, please cite our work (citation will be added upon publication).

---

## 📬 Contact

For questions or collaboration, please contact: [Your Email]
