# Expression Transfer on Face Meshes through 2D Monocular Guidance

This repository contains the implementation of our framework for **real-time expression transfer** on 3D facial meshes, guided by a single **2D monocular image**.  
The method deforms a neutral 3D face mesh so that it reproduces the expression of a target face, using **neural networks**, differentiable rendering, feature embeddings, and landmark supervision.

The full report, including result visualizations, is available [here](https://github.com/Puaison/Expression-transfer-on-Face-meshes-through-2D-monocular-guidance/blob/main/report.pdf).

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

## 📊 Quantitative Results

We compared against **Text2Mesh** (NSF) and **PyTorch3D** baseline.  
Our framework achieved **better scores in all similarity metrics** (Chamfer, Hausdorff, EMD) and up to **36× faster convergence**.

| Method     | Chamfer ↓ | Hausdorff ↓ | EMD ↓      | Time (min) ↓ |
|------------|-----------|-------------|------------|--------------|
| NSF        | 0.0988    | 0.0842      | 0.0974     | FAIL         |
| PyTorch3D  | 0.0251    | 0.0423      | 0.0273     | 6.41         |
| **Ours**   | **0.0244**| **0.0403**  | **0.0306** | **0.12**     |

---
