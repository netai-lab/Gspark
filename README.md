# GSpark: A Large-Scale Multimodal User-Behavior Dataset for Understanding 3D/4DGS Interaction

This dataset contains multimodal user behavior data (6DoF head poses and eye gaze) collected during immersive viewings of various 3D and 4D Gaussian Splatting (GS) models. It encompasses data from 81 participants exploring 12 high-fidelity scenes across four distinct categories.

## Dataset Organization

The dataset directory is organized as follows:

```text
ROOT/
├── Stimuli (Viewing Frames)/      # Sample view frames for different GS model categories
│   ├── "Content Name"_"Label"/    # Multiple render images for a specific content item
│   └── ...
├── "Category"_UserBehavior/       # Behavioral data collected for a specific GS category
│   ├── "Content Name"_"Label"/    # Behavioral data for a specific GS content item
│   │   ├── "UID"_"Content Name".csv  # User behavior trace (see below for format)
│   │   └── ...                    # Other users' traces
│   └── ...
├── Readme.md                      # This file, summarizing structure and data
└── LICENSE.txt                    # Usage license 
```

### Folder Explanations

- **`Stimuli (Viewing Frames)/`**: Contains sample view frames for different categories of GS models. Each content item has its own subfolder storing multiple render images representing the scene.
- **`"Category"_UserBehavior/`**: Dedicated folders for each type of GS content (e.g., Garden-scale, Large-scale, Dynamic Humans, Dynamic Full-scene). 
  - **`"Content Name"_"Label"/`**: Subfolders within the category folder that store all participants’ behavioral data for a specific content item. (Please refer to Table 2 in the paper for specific "Content Names").
  - **`"UID"_"Content Name".csv`**: The raw trace file for an individual user, where "UID" is a unique identifier assigned to the participant.

## Data Format (CSV)

During the experiment, the user's 6DoF poses (3D world coordinates and quaternions of the HMD) and eye gaze signals were recorded continuously. 

Each CSV file (`"UID"_"Content Name".csv`) contains the following columns:

| Column Name | Description | Unit / Format |
| :--- | :--- | :--- |
| `Timestamp` | Elapsed viewing time index, starting from the beginning of video playback/scene visualization. | Milliseconds (ms) |
| `Scene_X`, `Scene_Y`, `Scene_Z` | Head position in the virtual environment (Unity's left-handed coordinate system). | Meters (m) |
| `Head_RotX`, `Head_RotY`, `Head_RotZ` | Head orientation. | Degrees / Angular domain |
| `Eye_RotX`, `Eye_RotY`, `Eye_RotZ`, `Eye_RotW` | Eye gaze orientation, capturing the user’s gaze direction within the scene. Also determines convergence distance and eye origin mathematically combined with head pose. | World-space Quaternion |

### Coordinate System & Equipment
- **System**: Unity Engine (Left-handed coordinate system).
- **Equipment**: HTC VIVE Focus 3 Vision HMD with dual eye-tracking cameras (90 Hz). Data is typically sampled at 25–45 Hz, depending on rendering load.
- **Scale**: All GS models are rendered at a 1:1 scale to preserve geometric fidelity.

## Citation
If you use this dataset in your research, please cite the associated paper:

```bibtex
@inproceedings{gspark2026multimodal,
  title={Guided by Your Behavior: A Large-Scale Multimodal User-Behavior Dataset for Understanding 3D/4DGS Interaction},
  author={Anonymous Author(s)},
  booktitle={Proceedings of ACM Multimedia (MM'26)},
  year={2026},
  note={Under review}
}
```
