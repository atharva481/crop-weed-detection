

# 🌱 Crop & Weed Detection using YOLO

## Overview

This project implements a **real-time Crop and Weed Detection System** using the YOLO object detection framework. The model is trained to identify and localize crops and weeds in agricultural field images, enabling precision farming and reducing unnecessary herbicide usage.

The system can assist farmers and agricultural automation systems by accurately distinguishing between crops and weeds, supporting targeted weed management strategies.

---

## Features

* Real-time crop and weed detection
* Bounding box localization using YOLO
* Precision agriculture application
* Fast inference suitable for deployment
* Custom-trained model on agricultural imagery
* IoU-based evaluation metrics

---

## Project Architecture

```text
Input Field Image
        │
        ▼
 Image Preprocessing
        │
        ▼
 YOLO Object Detection Model
        │
        ▼
 Crop / Weed Classification
        │
        ▼
 Bounding Box Generation
        │
        ▼
 Detection Results
```

---

## Dataset

The model was trained on a custom agricultural dataset containing annotated images of:

* Crops
* Weeds

Annotations were created in YOLO format with bounding box coordinates for supervised object detection.

---

## Model Performance

### Validation Results

| Metric       | Score  |
| ------------ | ------ |
| Precision    | 80.82% |
| Recall       | 83.06% |
| mAP@0.5      | 84.04% |
| mAP@0.5:0.95 | 54.71% |

### Class-wise Performance

| Class | Precision | Recall | mAP@0.5 |
| ----- | --------- | ------ | ------- |
| Crop  | 75.5%     | 80.4%  | 84.4%   |
| Weed  | 86.5%     | 86.1%  | 84.0%   |

These results demonstrate strong detection capability for both crop and weed classes while maintaining efficient inference speed.

---

## Technologies Used

* Python
* YOLO
* OpenCV
* NumPy
* PyTorch
* Ultralytics

---

## Installation

### Clone Repository

```bash
git clone https://github.com/atharva481/crop-weed-detection.git
cd crop-weed-detection
```

### Create Virtual Environment

```bash
python -m venv venv
```

### Activate Environment

Windows:

```bash
venv\Scripts\activate
```

Linux/Mac:

```bash
source venv/bin/activate
```

### Install Dependencies

```bash
pip install -r requirements.txt
```

---

## Training

Train the YOLO model:

```bash
yolo detect train \
model=yolo11n.pt \
data=data.yaml \
epochs=100 \
imgsz=640
```

---

## Validation

```bash
yolo detect val \
model=runs/detect/train/weights/best.pt \
data=data.yaml
```

---

## Inference

Run prediction on an image:

```bash
yolo detect predict \
model=best.pt \
source=test.jpg
```

Run prediction on a video:

```bash
yolo detect predict \
model=best.pt \
source=test_video.mp4
```

---

## Sample Results

### Crop Detection

* Successfully identifies crop regions.
* Generates bounding boxes with confidence scores.

### Weed Detection

* Accurately localizes weeds among crop rows.
* Supports targeted weed management applications.

*(Add screenshots from your results folder here.)*

---

## Applications

* Precision Agriculture
* Smart Farming
* Automated Weed Removal Systems
* Agricultural Robotics
* Herbicide Optimization
* Crop Monitoring

---

## Future Improvements

* Multi-class weed species detection
* Drone-based field monitoring
* Real-time edge deployment on Raspberry Pi/Jetson Nano
* Integration with autonomous spraying systems
* Improved localization accuracy through larger datasets

---

## Results Summary

> Developed a YOLO-based Crop & Weed Detection System achieving **84.04% mAP@0.5**, **80.82% precision**, and **83.06% recall** on a custom agricultural dataset, enabling accurate identification of crops and weeds for precision farming applications.

---

## Author

**Atharva Sawant**

GitHub: [Atharva Sawant GitHub](https://github.com/atharva481?utm_source=chatgpt.com)

LinkedIn: Add your LinkedIn profile link here.

---

## License

This project is released under the MIT License. Feel free to use and modify it for educational and research purposes.
