# Real-Time Body and Pedestrian Detection using OpenCV

A lightweight Computer Vision pipeline developed to detect human bodies and pedestrians in video streams. This project utilizes traditional computer vision techniques, specifically *Haar Cascade Classifiers, combined with OpenCV's high-performance video processing capabilities to achieve real-time object localization.

## 📊 Project Highlights
 *Core Tool: Built completely using OpenCV (cv2) and NumPy.
 *Algorithm: Implemented the classical Haar Cascade Fullbody model for feature extraction and fast bounding box localization.
 *Data Processing: Handled frame-by-frame matrix manipulations, converting BGR images to Grayscale arrays to optimize execution speed.

---

## 🏗️ Technical Workflow

1. Video Ingestion:
    Handled video streams using `cv2.VideoCapture` to pull frame arrays sequentially.
    Leveraged validation flags (`ret`) to ensure proper video decoding and stream stability.

2. Image Transformation & Matrix Inspection:
    Inspected raw frame matrices (`dtype=uint8`) to verify image resolutions and array structures.
    Transformed BGR frames into Grayscale space using `cv2.cvtColor` with `cv2.COLOR_BGR2GRAY` to reduce data dimensionality from 3 channels to 1 channel before detection.

3. Multi-Scale Object Detection:
    Utilized `cv2.CascadeClassifier` loaded with `haarcascade_fullbody.xml`.
    Tuned hyper-parameters within the `.detectMultiScale()` method:
      *Scale Factor (1.2): Controls how much the image size is reduced at each image scale.
      **Min Neighbors

