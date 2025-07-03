# HematoVision 🩸🔬

> **HematoVision** is a lightweight, end‑to‑end deep‑learning pipeline that classifies microscopic blood‑cell images into four white‑blood‑cell (WBC) types—**Eosinophil, Lymphocyte, Monocyte**, and **Neutrophil**—in real time. It harnesses **MobileNetV2** transfer learning, a minimal **Flask** API, and a clean single‑page UI built with **Milligram CSS**.

---

## Table of Contents
- [Features](#)
- [Demo](#demo)
- [System Architecture](#)
- [Folder Structure](#folder-structure)
- [Training Your Own Model](#training-your-own-model)
- [Dataset](#dataset)
- [Results](#results)
- [Acknowledgements](#acknowledgements)

---

## Features
- ⚡ **Real‑time inference** (< 50 ms on CPU)
- 🏋️‍♂️ **Lightweight MobileNetV2** (~3.5 MB weights)
- 🖱️ **Drag‑and‑drop UI** (Milligram CSS + vanilla JS)
- 📊 **Metrics & visualisations** (confusion matrix, ROC curves)



## System Architecture
```mermaid
graph LR
    subgraph Frontend
        A[User Browser]
    end
    subgraph Backend
        B[Flask API /predict]
        C[(TensorFlow Model\nMobileNetV2)]
    end
    A -- "Image Upload" --> B
    B -- "Model Inference" --> C
    C -- "Predicted Label" --> B
    B -- "JSON Response" --> A
