# Expression Transfer on Face Meshes through 2D Monocular Guidance

<p align="center">
  <img src="images/architecture.png" width="600"/>
</p>

This repository contains the implementation of our framework for **real-time expression transfer** on 3D facial meshes, guided by a single **2D monocular image**.  
The method deforms a neutral 3D face mesh so that it reproduces the expression of a target face, using **neural networks**,ndifferentiable rendering, feature embeddings, and landmark supervision.

---

## 🎯 Motivation
Facial expression transfer is a key challenge in:
- 🎮 **Gaming** → realistic avatars and NPCs  
- 🎬 **Film & Animation** → automatic character rigging  
- 🩺 **Healthcare** → expression monitoring for rehabilitation

Unlike existing **neural network–based** frameworks (Text2Mesh, Pixel2Mesh), our method:
- Works **without large datasets** (zero-shot learning).  
- Is **fully automatic** and **real-time**.  
- Preserves **fine-grained facial details** (wrinkles, lineaments) of the mesh subject (maintaining his/her identity).  

---

## 🚀 Key Features

## 🚀 Key Features
- **Neural Networks for Mesh Deformation**  
  - *Multi-Layer Perceptron (MLP)* for fast landmark alignment.  
  - *Residual Network* for smooth feature-based deformations.  
- **Zero-Shot Learning** → No pre-collected dataset required.  
- **Differentiable Landmark Detection** → Automatic supervision from 2D keypoints.  
- **Feature Extraction with VGG16** → Multi-scale embeddings for realism.  
- **Flexible Pipelines** →  
  - *Moderate Facial Expressions (MFE)*: residual network only.  
  - *Exaggerated Facial Expressions (EFE)*: multi-stage MLP + residual. 
- **Superior Results** compared to PyTorch3D and Text2Mesh baselines.  

---

## 🧩 Framework Overview
<p align="center">
  <img src="images/figure_page4_1.png" width="600"/>
</p>

1. Extract **landmarks** and **features** from target 2D image.  
2. Render source mesh, extract the same descriptors.  
3. Neural networks (MLP or ResNet) generate vertex displacements along surface normals.  
4. Optimize using perceptual, landmark, pixel and regularization losses.  
5. Obtain a deformed mesh reproducing the target expression.  

---

## 📷 Visual Results

### 🔹 Landmark Extraction
<p align="center">
  <img src="images/landmarks.png" width="400"/>
</p>

### 🔹 Moderate Facial Expression (MFE)
<p align="center">
  <img src="images/mfe_results.png" width="700"/>
</p>

### 🔹 Exaggerated Facial Expression (EFE)
<p align="center">
  <img src="images/efe_results.png" width="700"/>
</p>

### 🔹 Comparisons with Baselines
<p align="center">
  <img src="images/comparison_baselines.png" width="700"/>
</p>

---

## 📊 Quantitative Results

We compared against **Text2Mesh** (NSF) and **PyTorch3D** baseline.  
Our framework achieved **better scores in all similarity metrics** (Chamfer, Hausdorff, EMD) and up to **36× faster convergence**.

| Method     | Chamfer ↓ | Hausdorff ↓ | EMD ↓      | Time (min) ↓ |
|------------|-----------|-------------|------------|--------------|
| NSF        | 0.0988    | 0.0842      | 0.0974     | FAIL         |
| PyTorch3D  | 0.0251    | 0.0423      | 0.0273     | 6.41         |
| **Ours**   | **0.0244**| **0.0403**  | **0.0306** | **0.12**     |

---
