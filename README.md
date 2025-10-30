# 🧬 Compress, Encode, Diagnose: PCA-Enhanced QNNs for Breast Cancer Classification

[![IEEE RASSE 2025](https://img.shields.io/badge/IEEE%20RASSE%202025-Accepted-success)](https://2025.ieee-rasse.org)
[![Conference](https://img.shields.io/badge/Conference-Nov%204--7%2C%202025-blue)]()
[![Location](https://img.shields.io/badge/Location-Singapore-red)]()
[![License](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)

> 🧠 *Accepted for presentation at the IEEE International Conference on Recent Advances in Systems Science and Engineering (IEEE RASSE 2025), Singapore — November 4–7, 2025.*

---

## 🧩 Overview

**Quantum Neural Networks (QNNs)** promise powerful new paradigms in learning by leveraging quantum superposition and entanglement — but are currently constrained by limited qubit counts.  
This work proposes a **hybrid quantum–classical neural network** that integrates **Principal Component Analysis (PCA)** for dimensionality reduction and **Variational Quantum Circuits (VQCs)** for quantum feature encoding.

Our study demonstrates that **PCA-enhanced QNNs** can outperform classical networks of comparable size on a **biomedical classification task (Breast Cancer Diagnosis)**, while maintaining **robustness under noise**.

---

## 🚀 Key Contributions

- 🧱 **Hybrid Architecture:** Combined PCA-based classical preprocessing with trainable quantum circuits using angle encoding and ring-topology entanglement.  
- ⚙️ **Quantum Circuits:** Implemented **5-qubit** and **10-qubit** Variational Quantum Circuits with parameter-shift gradient optimization.  
- 📉 **Comparative Baselines:** Benchmarked QNNs against classical MLPs with identical structure and parameter counts.  
- 🔬 **Noise Robustness:** Demonstrated quantum model resilience under additive Gaussian noise (σ = 5%, 10%, 50%).  
- 📈 **Performance:**  
  - **QNN-PCA-5** achieved **96.49% accuracy** and **0.97 F1-score**, outperforming the best classical baseline (95.61%).  
  - Retained strong performance under noise, showing **superior robustness** for biomedical settings.  

---

## 🧠 Methodology

### 1. Hybrid QNN Pipeline
Input Data → Normalization → PCA Compression → Variational Quantum Circuit (VQC) → Classical Output Layer → Prediction

- **PCA** reduces the original 30 features (WDBC dataset) into top 5 or 10 principal components.  
- **VQC** encodes features via rotation gates (angle encoding) and learns non-linear quantum feature transformations.  
- **Parameter-shift gradients** are used for end-to-end training in **PennyLane + PyTorch**.

### 2. Models Evaluated
| Model | Qubits | PCA | Accuracy | F1-score |
|--------|---------|-----|-----------|-----------|
| QNN-PCA-5 | 5 | ✅ | **96.49%** | **0.97** |
| QNN-RAW-5 | 5 | ❌ | 90.35% | 0.92 |
| QNN-RAW-10 | 10 | ❌ | 88.60% | 0.90 |
| Classical-PCA-5 | — | ✅ | 92.98% | 0.94 |
| Classical-RAW-30 | — | ❌ | 95.61% | 0.96 |

### 3. Robustness Tests
| Model | σ (Noise Std. Dev.) | Accuracy | F1-score |
|--------|----------------------|-----------|-----------|
| QNN-PCA-5 | 0.05 | 96.49% | 0.97 |
| QNN-PCA-5 | 0.10 | 96.49% | 0.97 |
| QNN-PCA-5 | 0.50 | 63.16% | 0.77 |
| Classical-PCA-5 | 0.50 | 18.42% | 0.24 |

---

## 🧪 Experimental Setup

- **Dataset:** Wisconsin Diagnostic Breast Cancer (569 samples, 30 features)  
- **Split:** 70% training / 30% testing (stratified)  
- **Optimization:** Adam optimizer, 100 epochs  
- **Backend:** [PennyLane](https://pennylane.ai) (statevector simulation) + PyTorch  
- **Metrics:** Accuracy, Precision, Recall, F1-score  

---

## 📊 Results Summary

| Key Finding | Insight |
|--------------|----------|
| PCA dramatically enhances quantum model learning efficiency | 5-qubit PCA-QNN > 10-qubit raw QNN |
| Quantum circuits show smoother generalization and higher recall | Especially valuable in medical diagnosis |
| PCA+QNN maintains accuracy under low noise levels | Robustness advantage over classical baselines |
| Increasing qubits without PCA reduces accuracy | Dimensional bottleneck re-emerges |

---

---

## 🧭 Discussion

- **Hybrid Synergy:** PCA leverages classical efficiency, while VQC offers high-capacity quantum feature mapping.
- **Practical Takeaway:** PCA-driven QNNs are a hardware-efficient path for current **NISQ-era** quantum systems.
- **Future Work:**  
  - Quantum PCA or autoencoder-based compression  
  - Real-device implementation and noise mitigation  
  - Scaling to image-based or multi-class biomedical data  

---

## 🏆 Authors & Acknowledgment

**Authors:**  
Aman Kumar Prajapati, Lupam Kumar Saha, **Mohammed Nabeel Ahsan**, Dr. Aswath Babu H  
**Affiliation:** Indian Institute of Information Technology, Dharwad (IIIT Dharwad)  
**Conference:** *IEEE International Conference on Recent Advances in Systems Science and Engineering (IEEE RASSE 2025)*  
**Dates:** November 4–7, 2025 | Singapore  
**Sponsor:** IEEE Systems Council  

---

## 🖥️ Repository Structure

