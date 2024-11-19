Bluetooth Drowsiness Detection Project Setup

Files to Include

1. README.md

Content for README.md

# Bluetooth Drowsiness Detection System

This project is a preliminary implementation of a drowsiness detection system that uses Bluetooth to communicate drowsiness alerts from a PC to a connected mobile device. The project serves as an exploration of how to establish a stable real-time connection between a PC-based server and a mobile app to enable efficient communication of alerts.

## Overview

The system uses a webcam to capture real-time video and processes the frames using `dlib`'s 68-point facial landmark predictor to detect eyes and calculate the eye aspect ratio (EAR). The EAR is used to determine if the user is drowsy by comparing it against a predefined threshold.

If drowsiness is detected, an alert is sent via Bluetooth to a paired mobile device.

**Technologies Used:**
- Python
- OpenCV
- Dlib
- Bluetooth communication (`pybluez`)

## How It Works
- Detects the user's face using `dlib`'s frontal face detector.
- Extracts facial landmarks, particularly the eyes, using a pre-trained `shape_predictor_68_face_landmarks.dat` model.
- Computes the eye aspect ratio (EAR) to determine whether the eyes are closed for a prolonged period, indicating drowsiness.
- Displays real-time video using `OpenCV` with overlaid markers to indicate drowsiness.
- If drowsiness is detected, sends an alert message via Bluetooth to a connected mobile device.

## Getting Started

### Prerequisites

Make sure you have Python 3.8+ installed. You'll need the following libraries:

- `dlib` - for facial landmark detection.
- `opencv-python` (`cv2`) - for video stream handling.
- `scipy` - for spatial distance calculation.
- `pybluez` (`bluetooth`) - for Bluetooth communication.
- `numpy` - for numerical operations.

### Installation

1. Clone the repository:

   ```bash
   git clone <repository-url>
   cd bluetooth-drowsiness-alert

Install the dependencies:

pip install -r requirements.txt

Download the shape_predictor_68_face_landmarks.dat file from dlib's Model Zoo and place it in the root of the project folder.

Usage

Run the following command to start the detection system:

python bluetooth_drowsiness_detection.py

Press q to quit the webcam feed.

Note

Make sure your webcam is connected and accessible.

Ensure Bluetooth is enabled and the PC is paired with the mobile device.

The default threshold values are set based on standard averages; you may need to tweak them for better results depending on individual differences.

Future Work

This project serves as a test implementation and will be integrated with an Android mobile application to improve driver safety by alerting users about their drowsiness state.
