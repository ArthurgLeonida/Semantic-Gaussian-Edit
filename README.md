# Semantic Gaussian Edit: Text-Guided 3D Scene Manipulation

[![License](https://img.shields.io/badge/License-Gaussian--Splatting-gray.svg)](LICENSE)
[![Python](https://img.shields.io/badge/Python-3.8+-blue.svg)](https://www.python.org/)
[![Pytorch](https://img.shields.io/badge/PyTorch-2.0+-ee4c2c.svg)](https://pytorch.org/)

**Author:** Arthur Leonida  
**Institution:** Federal University of Santa Catarina (UFSC)  
**Context:** Undergraduate Thesis (TCC / Final Course Project)

## 📄 Abstract

This project aims to develop a pipeline for **text-guided 3D scene editing** by combining the real-time rendering capabilities of **3D Gaussian Splatting (3DGS)** with the generative semantic knowledge of **Diffusion Models** (e.g., Stable Diffusion / InstructPix2Pix).

While 3DGS provides state-of-the-art reconstruction quality, modifying these explicit representations remains a challenge. This framework introduces an iterative optimization method to apply semantic edits (e.g., *"Turn the car into gold"*) while preserving the geometric consistency of the original scene.

## 🏗️ Architecture (Proposed)

The pipeline consists of three main modules:
1.  **Reconstruction:** Generating a 3D Gaussian Splatting representation from sparse input images.
2.  **2D Editing:** Rendering views of the scene and applying text-guided edits using a conditional Diffusion Model.
3.  **3D Update:** Backpropagating the 2D edits to the 3D Gaussian parameters (Color/SH) using a directional loss (e.g., SDS or Iterative Dataset Update).

## 🗺️ Roadmap

- [ ] **Phase 1: Foundation**
    - [x] Set up environment and dependencies.
    - [ ] Reproduce original 3DGS results on custom dataset.
- [ ] **Phase 2: Integration**
    - [ ] Implement `Editor` class to interface with Hugging Face Diffusers.
    - [ ] Create `train_edit.py` for the joint optimization loop.
- [ ] **Phase 3: Refinement**
    - [ ] Implement view-consistency checks.
    - [ ] Evaluate metrics (CLIP Score, PSNR vs. Original).

## 🛠️ Installation

This repository is built upon the original [3D Gaussian Splatting](https://github.com/graphdeco-inria/gaussian-splatting) codebase.

```bash
# Clone the repository
git clone --recursive [https://github.com/YOUR-USERNAME/Semantic-Gaussian-Edit.git](https://github.com/YOUR-USERNAME/Semantic-Gaussian-Edit.git)
cd Semantic-Gaussian-Edit

# Create the environment
conda env create --file environment.yml
conda activate gaussian_splatting

# Install submodules
pip install -r requirements.txt

## 🚀 Usage

(Coming soon. This section will detail how to run the editing pipeline.)

## 📚 References & Acknowledgments

This project is built on the shoulders of giants. Special thanks to the authors of the following works:

3D Gaussian Splatting for Real-Time Radiance Field Rendering (Kerbl et al., 2023) - Repository

InstructPix2Pix: Learning to Follow Image Editing Instructions (Brooks et al., 2023)

DreamCatalyst (Shim et al., 2025) - Inspiration for the optimization strategy.
