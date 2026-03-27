# GSpark: A Multimodal User-Behavior Dataset for 3D/4DGS Interaction

This repository contains the GSpark dataset, which provides multimodal user behavior data—including 6DoF head poses and eye gaze signals—collected from users interacting with various categories of 3D/4D Gaussian Splatting (GS) models in virtual environments.

## 📁 Dataset Organization

The dataset directory is organized as illustrated in Figure 3. It is structured hierarchically by GS category, content name, and user ID to ensure easy navigation:

```text
ROOT/
├── Stimuli/                           
│   ├── <Content Name>_<Label>/        # Contains sample view frames (render images) for this specific GS content
│   └── ...
├── <Category>_UserBehavior/           # Behavioral data grouped by GS content type
│   ├── <Content Name>_<Label>/        # Contains all participants' behavioral data for this specific content
│   │   ├── <UID>_<Content Name>.csv   # Individual CSV file containing the user's recorded trace
│   │   └── ...
│   └── ...
└── Readme.md                          # Data acquisition system, parameters, and structural details
Column Name,Description,Unit / Format
Timestamp,Elapsed time since the start of the scene,Milliseconds (ms)
"Scene_X, Scene_Y, Scene_Z",3D world coordinates (position) of the HMD in the virtual environment,Meters (m)
"Head_RotX, Head_RotY, Head_RotZ",6DoF head orientation (rotation),Angular domain
"Eye_RotX, Eye_RotY, Eye_RotZ, Eye_RotW","Eye gaze orientation, indicating gaze direction and convergence distance",World-space Quaternion
