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





# Real-Time Human Pose Estimation & Tracking using YOLOv8

A state-of-the-art Computer Vision pipeline leveraging the *YOLOv8-Pose architecture to perform high-speed human detection, tracking, and skeletal keypoint extraction from video streams. This system processes dynamic video inputs natively on CUDA, delivering raw localization tensors for downstream behavioral analysis.

## 📊 Project Highlights
 *Model Backbone: Implemented YOLOv8-Pose (`yolov8n-pose.pt`) via the Ultralytics framework.
 *Hardware Acceleration: Fully bound to CUDA GPU execution (`device='cuda:0'`) for low-latency inference.
 *Data Extraction: Successfully parsed prediction objects into bounding box coordinates, class confidence levels, and segmentation/pose indices.

---

## 🏗️ Technical Workflow & Tensor Anatomy

1. Video Streaming Pipeline:
    Handled directory pathing using Python's native `os.path` module to isolate local video assets (`.mov` / `.mp4` formats).
    Loaded the source stream into the YOLO inference engine with a tuned confidence threshold (`conf=0.5`).

2. Inference Metrics & Speed:
    Benchmark performance verified at: *2.4ms preprocess, 20.2ms inference, and 1.4ms postprocess per image frame, running comfortably above real-time requirements (approx. 40+ FPS).

3. Tensor Extraction & Parsing:
    *Bounding Boxes (`boxes.xyxy`):* Extracted accurate spatial coordinates representing $
