Vehicle Speed Estimation using Computer Vision

This project implements a complete vehicle speed estimation pipeline using YOLOv8 for object detection, BYTETrack for multi-object tracking, and OpenCV for perspective correction and speed computation.
It accurately converts pixel motion into real-world speed metrics through homography-based perspective transformation and temporal averaging, ensuring stable and precise results.

Features

Vehicle detection using YOLOv8

Multi-object tracking with BYTETrack

Perspective distortion correction using homography mapping

Speed estimation with temporal averaging for accuracy and stability

Easily extendable to other object detection models

Project Structure
├── data/                # Input videos and test data
├── notebooks/           # Example Jupyter notebooks
├── scripts/             # Core scripts for detection, tracking, and speed estimation
├── results/             # Output videos and visualizations
├── requirements.txt     # Python dependencies
└── README.md            # Project documentation

Installation

Clone this repository

git clone https://github.com/your-username/vehicle-speed-estimation.git
cd vehicle-speed-estimation


Create a virtual environment (recommended)

python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate


Install dependencies

pip install -r requirements.txt

Usage

Place your input video (e.g., vehicles.mp4) in the data/ folder.

Run the main script:

python scripts/speed_estimation.py


The processed video with annotated detections and estimated speeds will be saved in the results/ directory.

How It Works

Object Detection:
YOLOv8 detects vehicles in each frame of the video.

Tracking:
BYTETrack assigns consistent IDs to each vehicle across frames for continuous tracking.

Perspective Transformation:
OpenCV’s getPerspectiveTransform is used to correct for camera perspective distortion using a homography matrix.

Speed Calculation:
The distance traveled by each vehicle in the transformed coordinate space is divided by time, then averaged over multiple frames to ensure stable and realistic speed estimates.
