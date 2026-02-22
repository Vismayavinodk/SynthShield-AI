# 🛡️ SynthShield-AI  
### Build → Break → Improve: Strengthening AI-Generated Image Detection

SynthShield-AI is a deep learning pipeline designed to detect AI-generated (fake) images, evaluate model vulnerabilities through adversarial attacks, and improve robustness using adversarial defense techniques.

This project follows a structured **Build → Break → Improve** methodology to analyze and strengthen AI image detection systems.

---

## 🚀 Motivation

With the rapid advancement of generative models, distinguishing between real and AI-generated images has become increasingly difficult. While deep learning detectors achieve high accuracy on clean data, they can still be vulnerable to adversarial manipulation.

SynthShield-AI demonstrates:

- How a high-performing classifier can be fooled
- How adversarial perturbations affect prediction confidence
- How robustness can be improved through adversarial training
- Why explainability matters in AI security systems

---

## 🧩 Pipeline Overview

### 🔹 Phase 1 — Build (Baseline Model)

- Dataset: CIFAKE (Real vs AI-generated images)
- Model: Pretrained ResNet18 fine-tuned for binary classification
- Output classes:
  - 0 → FAKE  
  - 1 → REAL  
- Evaluation metrics:
  - Accuracy
  - Confusion matrix
  - Sample predictions

Goal: Train a high-confidence fake image detector capable of distinguishing synthetic content from real images.

---

### 🔹 Phase 2 — Break (Adversarial Attack)

We implemented a **targeted iterative FGSM attack** to flip predictions from FAKE → REAL.

Key steps:
- Select high-confidence FAKE samples
- Apply small, bounded perturbations
- Perform iterative gradient-based updates
- Track fake confidence drop across attack steps
- Visualize adversarial examples

Results:
- Successful prediction flipping
- Significant reduction in fake confidence
- Images remained visually indistinguishable to humans

This phase demonstrates that even accurate models are vulnerable to adversarial manipulation.

---

### 🔹 Phase 3 — Improve (Defense & Robustness)

To strengthen the detector:

- Introduced adversarial training
- Retrained the model using adversarial samples
- Compared baseline vs defended model performance
- Applied Grad-CAM to analyze attention regions

Results:
- Improved resistance to adversarial attacks
- More stable prediction confidence under perturbation
- Better focus on semantically meaningful image regions

This phase shows how robustness techniques can mitigate adversarial vulnerabilities.

---

## 📊 Key Observations

| Stage     | Outcome |
|-----------|----------|
| Baseline  | High accuracy on clean images |
| Attack    | Successful targeted prediction flipping |
| Defense   | Improved robustness and confidence stability |

The project highlights the importance of adversarial robustness in real-world AI deployment.

---

## 🧠 Technical Details

- Backbone: ResNet18 (pretrained on ImageNet)
- Final Layer: Modified for binary classification
- Loss Function: CrossEntropyLoss
- Optimizer: Adam
- Attack Method: Targeted Iterative FGSM
- Defense Strategy: Adversarial training
- Explainability: Grad-CAM visualization

---

## 📂 Repository Structure

SynthShield-AI/
│
├── README.md
├── requirements.txt
│
├── notebooks/
│ └── SynthShield.ipynb
│
├── models/
│ ├── guardian_stage1.pth
│ └── guardian_final.pth
│
├── results/
│ ├── adversarial_examples.png
│ ├── confidence_trajectory.png
│ ├── confusion_matrix.png
│ └── gradcam_example.png
│
└── report/
└── SynthShield_Report.pdf


---

## ⚙️ Installation & Usage

### 1️⃣ Clone the Repository

git clone https://github.com/Vismayavinodk/SynthShield-AI.git
cd SynthShield-AI

### 2️⃣ Install Dependencies

pip install -r requirements.txt

### 3️⃣ Run the Notebook

jupyter notebook notebooks/SynthShield.ipynb

The notebook contains the complete Build → Break → Improve workflow.

---

## 🔎 Explainability

Grad-CAM visualizations are used to:

- Interpret model focus regions
- Compare attention before and after adversarial perturbation
- Validate robustness improvements

This adds interpretability to adversarial robustness analysis.

---

## 🎯 Impact

SynthShield-AI demonstrates:

- The fragility of AI detectors under adversarial pressure
- The importance of robustness in synthetic media detection
- A practical evaluation pipeline for secure AI systems

---

## 👥 Team

- Vismaya k
- Vaishnavi V
- Aswathy Menon

---

## 📜 License

This project is developed for academic and hackathon purposes.

