# 🖼️ Copy-Move Image Forgery Localization using VGG16 + FPN  
![Python](https://img.shields.io/badge/Python-3.10-blue?logo=python)
![TensorFlow](https://img.shields.io/badge/TensorFlow-2.x-orange?logo=tensorflow)
![Deep Learning](https://img.shields.io/badge/Deep%20Learning-FPN%20+%20VGG16-green)
![Dataset](https://img.shields.io/badge/Dataset-CoMoFoD-red)
![Computer Vision](https://img.shields.io/badge/Domain-Computer%20Vision-yellow)
![Status](https://img.shields.io/badge/Status-Completed-success)
![License](https://img.shields.io/badge/License-Academic-lightgrey)

---

## ✨ Project Overview  

🔍 **Image Forgery** is the manipulation of digital images to deceive or mislead viewers by altering content. Among different forgery types, **Copy-Move Forgery (CMF)** is one of the most common, where a part of an image is copied and pasted within the same image to conceal or emphasize certain information.  

This project focuses on **localization** (pinpointing the manipulated regions) rather than just **detection** (finding if an image is tampered or not).  

We implemented a **Feature Pyramid Network (FPN)** with **VGG16 backbone** to effectively localize forged regions, even under transformations like scaling, rotation, and noise addition.  

---

## 📌 Problem Statement  

➡️ Detect and localize **copy-move forgery** in digital images.  
➡️ Handle transformations such as **scaling, rotation, translation, and distortion**.  
➡️ Improve robustness against **post-processing methods** like JPEG compression, blurring, and noise addition.  

---

## 🧠 Abstract & Scope  

🎯 **Objective:** Detect and localize CMF regions using a **VGG16-based Feature Pyramid Network (FPN)**.  
📂 **Dataset:** [CoMoFoD](https://ieeexplore.ieee.org/document/6619032) (Copy-Move Forgery Detection) Dataset.  
⚡ **Why Deep Learning?**  
- Learns features automatically (no manual engineering like SIFT/SURF).  
- Robust to lighting, noise, and complex manipulations.  
- Handles large-scale and complex images better than traditional methods.  

---

## 📚 Literature Survey  

| Paper | Model | Drawbacks |
|-------|-------|-----------|
| Copy-move Image Forgery Localization Using Deep Feature Pyramidal Network [1] | BusterNet (DNN), VGG-FPN | BusterNet lower performance, VGG resolution limits |
| Multiple CMF Detection Based on Density Clustering [2] | AKAZE + DBSCAN | Hard to detect subtle forgeries |
| Optimized Pre-trained DL Model [3] | GoogLeNet + FLHHO | Needs large labeled dataset |
| CMF Detection with Deep Learning [4] | CNN (ImageNet Pretrained) | Struggles with real-world domain adaptation |

---

## ⚙️ Methodology  

✅ **Model:** VGG16 + Feature Pyramid Network (FPN)  
✅ **Pretrained Weights:** ImageNet  
✅ **Training Dataset:** CoMoFoD (10,400 images)  
✅ **Workflow:**  

1. 📂 Load Dataset (Organize into Train/Test/Validation)  
2. 🛠️ Define Model & Load Pretrained Weights  
3. ⚡ Compile Model & Initialize Callbacks  
4. 🔁 Train Model (20 epochs)  
5. 📊 Evaluate on Test Set  
6. 🎨 Visualize Forged Regions with Predicted Masks  

---

## 🏗️ Architecture  

- **Bottom-up pathway (VGG16):** Robust feature extraction  
- **Top-down pathway (FPN):** Multi-scale feature detection + upsampling  
- **Lateral connections:** Merge high- and low-level features  
- **Output:** Segmentation mask highlighting forged regions  

---

## 📂 Dataset: CoMoFoD  

- **Size:** 10,400 images  
- **Categories:** 260 forged image sets  
- **Sizes:** 512×512 (small), 3000×2000 (large)  
- **Transformations:** translation, rotation, scaling, distortion  
- **Post-processing:** JPEG compression, blurring, noise, color reduction  

📌 Naming Scheme:  
- `O` → Original  
- `F` → Forged  
- `M` → Colored Mask  
- `B` → Binary Mask  
### 🖼️ Dataset Samples
#### Example 1 & 2
<img width="719" height="377" alt="image" src="https://github.com/user-attachments/assets/f6d1e234-637d-44fa-be5f-2cb0aa9e88e9" />

#### Example 3 & 4
<img width="640" height="322" alt="image" src="https://github.com/user-attachments/assets/820d0e1a-d8ac-4c93-9d21-8fbba92fa13a" />

---

## 🛠️ Technologies Used  

- **Programming Language:** Python 🐍  
- **Libraries:**  
  - `opencv-python (cv2)` – Image Processing  
  - `numpy` – Numerical Computation  
  - `tensorflow.keras` – Deep Learning Framework  
  - `matplotlib` – Visualization  
  - `tqdm` – Progress Tracking  
- **Platform:** Kaggle (GPU T4x2)  

---

## 📊 Results  

| Metric | Score |
|--------|-------|
| **Accuracy** | 🎯 98.62% |
| **Precision** | 📏 91.20% |
| **Recall** | 🔁 83.23% |
| **DSC (Dice Similarity Coefficient)** | 86.19% |
| **IoU (Intersection over Union)** | 79.20% |

✅ **Training Accuracy:** 99.82%  
✅ **Validation Accuracy:** 98.82%  
✅ **Test Accuracy:** 98.62%  

### 🖼️ Sample Outputs
#### Example 1 & 2
<img width="584" height="344" alt="image" src="https://github.com/user-attachments/assets/fcc36c3d-6b16-456e-919d-e590e728bde7" />

#### Example 3 & 4
<img width="639" height="392" alt="image" src="https://github.com/user-attachments/assets/034485e6-bef7-4f24-901f-fc7c80fe10bc" />

---

## 📝 Conclusion & Future Work  

✔️ Successfully implemented **VGG16-FPN** for **copy-move forgery localization**.  
✔️ Achieved **high accuracy (98.62%)** with strong robustness against transformations.  

🚀 **Future Directions:**  
- Train on **multiple datasets** for better generalization.  
- Improve performance under **JPEG compression & noise**.  
- Reduce **false positives** with enhanced feature extraction.  
- Extend training for **higher epochs** to further improve accuracy.  

---


## 📖 References  

1. Sabeena M., Abraham L., Sreelekshmi P.R. – Copy-move Image Forgery Localization Using Deep Feature Pyramidal Network, *ICACC 2021*.  
2. Zhou X.H., Shi Q.J. – Multiple Copy-Move Forgery Detection Based on Density Clustering, *Pattern Recognit. Image Anal., 2021*.  
3. Chaitra B., Bhaskar Reddy P.V. – Optimized Deep Learning Model for CMF Detection, *Knowledge-Based Systems, 2023*.  
4. Ouyang J., Liu Y., Liao M. – CMF Detection using Deep Learning, *CISP-BMEI 2017*.  
5. Tralic D., Zupancic I., Grgic S., Grgic M. – CoMoFoD Dataset, *ELMAR 2013*.  

---

## 🏷️ Tags  

`#DeepLearning` `#ComputerVision` `#ForgeryDetection`  
`#CopyMoveForgery` `#VGG16` `#FPN`  
`#ImageProcessing` `#CoMoFoD` `#TensorFlow`  

---

