# GSpark Dataset

<p align="center">
  <b>Dataset for Gaussian Splatting Content with 6DoF Head Pose and Eye Gaze</b>
</p>

---

## 📌 Overview

GSpark is a dataset that provides synchronized **6DoF head pose** and **eye gaze signals** for various categories of Gaussian Splatting (GS) content in a virtual environment. It includes both rendered stimuli and user behavioral data for immersive viewing analysis.

---

## 🖼️ Dataset Structure

<p align="center">
  <img src="assets/fig3_structure.png" width="600"/>
</p>

<p align="center">
  <i>Figure 1: Folder structure of the GSpark dataset.</i>
</p>

### 📁 Directory Layout
ROOT/
├── Stimuli/ # Viewing frames
│ ├── ContentName_Label/
│ │ ├── image_001.png
│ │ ├── ...
│
├── Category_UserBehavior/ # Behavioral data
│ ├── ContentName_Label/
│ │ ├── UID_ContentName.csv
│ │ ├── ...
│
├── README.md

### Description

- **Stimuli/**  
  Rendered view frames for each GS content item  

- **Category_UserBehavior/**  
  Behavioral data grouped by content category  

- **Naming Rule**
- UID_ContentName.csv
- 
---

## 🧠 Data Description

### ⏱ Timestamp

- `Timestamp` (ms):  
Time elapsed since the start of scene playback  

---

### 🎯 Head Pose (6DoF)

- Position (meters):
- Scene_X, Scene_Y, Scene_Z
- Rotation (Euler angles):
- Head_RotX, Head_RotY, Head_RotZ
- 
---

### 👁 Eye Gaze

- Quaternion (world space):
- Eye_RotX, Eye_RotY, Eye_RotZ, Eye_RotW
- 
- Additional:
- Eye origin (3D)
- Gaze direction vector
- Convergence distance (m)

---

## ⚙️ Data Acquisition

- Platform: Unity virtual environment  
- Signals:
- 6DoF head motion  
- Eye tracking  
- Fully time-synchronized recordings  

---

## 📊 (Optional) Statistics

| Metric | Value |
|------|------|
| #Users | XX |
| #Scenes | XX |
| Duration | XX hours |

---

## 📖 Citation

```bibtex
@article{gspark_dataset,
title={...},
author={...},
year={...}
}
