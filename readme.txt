# Badminton Shuttlecock Tracking and Trajectory Analysis

A computer vision project for detecting, tracking, and analyzing shuttlecock movement in badminton videos.

This project applies **TrackNetV3** and its trajectory rectification workflow to detect the shuttlecock frame by frame, reconstruct missing trajectory points, and generate visual tracking results.

The project was developed as an academic and portfolio project focusing on computer vision, deep learning inference, video processing, and sports data analysis.

## Project Overview

Tracking a shuttlecock is challenging because it:

- Moves at very high speed
- Appears very small in video frames
- Is frequently affected by motion blur
- Can be temporarily hidden by players or rackets
- May blend into bright backgrounds and court lighting

This project uses a deep-learning-based tracking workflow to locate the shuttlecock and produce a more complete trajectory from badminton video footage.

## Main Features

- Detect shuttlecock positions frame by frame
- Track shuttlecock movement across video frames
- Reconstruct temporarily missing trajectory points
- Reduce noisy or incorrect detections
- Process badminton videos using Google Colab
- Generate annotated video results
- Export shuttlecock coordinates for further analysis
- Visualize shuttlecock movement and trajectory
- Test the system using a sample badminton video

Depending on the analysis workflow in the notebook, the generated tracking data can also be used for:

- Trajectory smoothing
- Missing-coordinate interpolation
- Movement direction analysis
- Speed estimation
- Shot trajectory comparison
- Basic badminton shot classification

## Processing Pipeline

```text
Input badminton video
        │
        ▼
Video frame extraction
        │
        ▼
TrackNetV3 shuttlecock detection
        │
        ▼
Trajectory rectification
        │
        ▼
Noise removal and missing-point reconstruction
        │
        ▼
Trajectory analysis and visualization
        │
        ▼
Annotated video and coordinate data
```

## Tech Stack

- **Python**
- **PyTorch**
- **OpenCV**
- **NumPy**
- **Pandas**
- **Matplotlib**
- **Jupyter Notebook**
- **Google Colab**
- **TrackNetV3**
- **InpaintNet**

## Repository Structure

```text
shuttlecock_tracking/
├── TrackNetV3/
│   ├── model definitions
│   ├── prediction scripts
│   ├── processing utilities
│   └── requirements.txt
├── notebook.ipynb
├── MyVideo-1.mp4
└── README.md
```

## Demo

A sample badminton video used for testing is included in this repository:

[View Sample Video](./MyVideo-1.mp4)

The notebook processes the input video and generates shuttlecock tracking results.

## Getting Started

### Recommended Environment

The easiest way to run this project is with:

- Google Colab
- Python 3
- GPU runtime
- Google Drive

A CUDA-enabled GPU is recommended because deep-learning inference may be slow on a CPU.

## Installation and Setup

### 1. Clone the Repository

```bash
git clone https://github.com/F74117043/shuttlecock_tracking.git
cd shuttlecock_tracking
```

Alternatively, download the repository as a ZIP file from GitHub.

### 2. Upload the Project to Google Drive

Upload the following files to a folder in Google Drive:

```text
Shuttlecock/
├── TrackNetV3/
├── notebook.ipynb
└── input-video.mp4
```

For example:

```text
MyDrive/Shuttlecock/
```

### 3. Open the Notebook

Open:

```text
notebook.ipynb
```

using Google Colab.

### 4. Enable GPU Acceleration

In Google Colab, select:

```text
Runtime → Change runtime type → T4 GPU
```

### 5. Mount Google Drive

Run the following code inside the notebook:

```python
from google.colab import drive

drive.mount("/content/drive")
```

### 6. Enter the Project Directory

Adjust the path according to where the project is stored:

```python
%cd /content/drive/MyDrive/Shuttlecock/TrackNetV3
```

### 7. Install Dependencies

Install the required Python packages:

```python
!pip install -r requirements.txt
```

Additional libraries may be installed inside the notebook when required.

### 8. Prepare the Model Weights

The pretrained TrackNetV3 and trajectory rectification model weights may need to be downloaded separately.

Common weight files include:

```text
TrackNet_best.pt
InpaintNet_best.pt
```

Place them inside the appropriate project or model directory.

Refer to the original TrackNetV3 repository for its pretrained model instructions.

### 9. Prepare an Input Video

Upload a badminton video to Google Colab or Google Drive.

For example:

```text
/content/input-video.mp4
```

Update the input video path inside the notebook so that it points to the correct file.

### 10. Run the Notebook

Run the notebook cells from top to bottom.

The notebook will:

1. Load the required libraries
2. Load the TrackNetV3 models
3. Read the badminton video
4. Detect shuttlecock positions
5. Process the predicted trajectory
6. Generate tracking outputs
7. Display or save the results

## Expected Outputs

Depending on the configuration, the project may generate:

```text
output/
├── tracked-video.mp4
├── shuttlecock-coordinates.csv
├── trajectory-visualization.png
└── processed-trajectory.csv
```

### Output Description

| Output | Description |
|---|---|
| Tracked video | Video with detected shuttlecock positions or trajectory |
| Coordinate CSV | Frame-by-frame shuttlecock coordinates |
| Trajectory image | Visualization of shuttlecock movement |
| Processed data | Cleaned or reconstructed trajectory information |

Actual filenames may differ depending on the notebook configuration.

## Coordinate Data

The generated coordinate data may contain information such as:

| Column | Description |
|---|---|
| Frame | Video frame number |
| Visibility | Whether the shuttlecock was detected |
| X | Horizontal shuttlecock coordinate |
| Y | Vertical shuttlecock coordinate |

This data can be used for additional analysis, including speed, direction, trajectory shape, and badminton shot characteristics.

## Screenshots

Screenshots or result visualizations can be stored in:

```text
assets/
```

Example README usage:

```markdown
![Shuttlecock Tracking Result](assets/tracking-result.png)
```

Recommended images to include:

- Original badminton video frame
- Shuttlecock detection result
- Completed shuttlecock trajectory
- Coordinate or trajectory graph
- Annotated output video frame

## My Contribution

My work in this project includes:

- Preparing the TrackNetV3 workflow for Google Colab
- Integrating the model with badminton video input
- Configuring video and model file paths
- Running shuttlecock detection and trajectory processing
- Testing the system using sample badminton footage
- Processing and visualizing the tracking results
- Organizing the project as an academic and portfolio repository
- Documenting the setup and execution workflow

The underlying TrackNetV3 architecture and pretrained models were developed by the original TrackNetV3 authors.

## Project Motivation

This project was created to explore the application of computer vision and deep learning in sports analysis.

It also helped me develop practical skills in:

- Computer vision
- Deep-learning inference
- Small-object tracking
- Video processing
- Trajectory analysis
- Python programming
- Google Colab workflow
- Data visualization
- Git and GitHub

## Current Development Status

The current repository provides a notebook-based workflow for running shuttlecock tracking experiments.

It is mainly designed for academic demonstration and portfolio purposes rather than production deployment.

The results may vary depending on:

- Camera angle
- Video resolution
- Frame rate
- Lighting conditions
- Motion blur
- Shuttlecock visibility
- Player occlusion
- Model weight quality

## Limitations

- The shuttlecock may be missed during very fast movement.
- Motion blur can reduce detection accuracy.
- Players, rackets, and court objects may temporarily hide the shuttlecock.
- Bright backgrounds may produce incorrect detections.
- Tracking quality depends heavily on the input video.
- Estimated speed is not guaranteed to represent real-world speed without camera calibration.
- The current workflow is not designed for real-time deployment.
- Model weights may need to be downloaded separately.
- The project currently requires manual path and notebook configuration.

## Future Improvements

Possible future improvements include:

- Camera calibration for real-world speed measurement
- Automatic court-line detection
- Improved outlier removal
- Better trajectory smoothing
- Automatic rally segmentation
- Player and racket detection
- More accurate shot classification
- Smash detection and analysis
- Real-time shuttlecock tracking
- Web-based video upload
- Interactive trajectory visualization
- Quantitative evaluation with labeled test videos
- Deployment as a web application

## Attribution

This project uses and adapts components from:

**TrackNetV3: Enhancing ShuttleCock Tracking with Augmentations and Trajectory Rectification**

Original repository:

```text
https://github.com/qaz812345/TrackNetV3
```

TrackNetV3 was developed for shuttlecock localization and trajectory rectification.

Please refer to the original repository and research paper for:

- Model implementation
- Pretrained weights
- Dataset information
- Licensing terms
- Citation requirements

## Disclaimer

This repository is an academic and portfolio project.

The TrackNetV3 model, source code, research, and pretrained weights belong to their respective original authors. This repository does not claim ownership of the original TrackNetV3 architecture.

## Author

**Dave Vicdelson Yoeh**

Computer Science student interested in computer vision, artificial intelligence, web development, and sports data analysis.

GitHub: [F74117043](https://github.com/F74117043)
