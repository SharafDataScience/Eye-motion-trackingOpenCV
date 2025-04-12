![image](https://github.com/user-attachments/assets/478fbd42-cc29-4523-9c96-e2067a183875)
# Face Tracking with Dlib & OpenCV

This project demonstrates real-time face detection and facial landmark tracking using **Dlib** and **OpenCV**. It uses Dlib's pre-trained 68-point facial landmark predictor to identify key points on detected faces through a webcam feed.

## Features

- Real-time face detection from a webcam.
- 68-point facial landmark tracking.
- Visual display of detected faces and landmarks.
- Clean OpenCV interface for easy visualization.

## Files

- `FaceTrackingDlib&OpenCV.ipynb`: Jupyter notebook containing the main implementation.
- `shape_predictor_68_face_landmarks.dat`: Pre-trained model file required for landmark detection (not included — see setup below).

## Getting Started

### Prerequisites

Install the required Python packages:

```bash
pip install opencv-python dlib

