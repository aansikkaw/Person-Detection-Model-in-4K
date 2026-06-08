# 👁️ 4K Computer Vision: Automated Person Detection & Analytics Pipeline

<div align="left">
  <img src="https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white" alt="Python" />
  <img src="https://img.shields.io/badge/YOLOv8-00FFFF?style=for-the-badge&logo=yolo&logoColor=black" alt="YOLOv8" />
  <img src="https://img.shields.io/badge/OpenCV-5C3EE8?style=for-the-badge&logo=opencv&logoColor=white" alt="OpenCV" />
  <img src="https://img.shields.io/badge/AI-Computer_Vision-00599C?style=for-the-badge" alt="Computer Vision" />
</div>

## 📌 Executive Summary
This repository contains an end-to-end Computer Vision pipeline utilizing the **YOLOv8** object detection architecture and **OpenCV**. 

Unlike standard detection scripts that simply overlay bounding boxes on low-resolution webcams, this system was explicitly engineered for **high-resolution (4K) video feeds**. Furthermore, it goes beyond real-time inference by extracting frame-by-frame telemetry (bounding box coordinates, object counts, and confidence thresholds) and compiling it into an automated, interactive HTML analytics dashboard.

---

## ⚙️ Key Engineering Features

### 1. 4K-Optimized Dynamic Rendering
Standard bounding boxes become invisible or distorted on ultra-high-definition footage. This pipeline includes a custom `draw_enhanced_bbox_4k` algorithm that mathematically scales bounding box thickness, typography, and UI elements relative to the input resolution (1080p vs. 4K), ensuring visual fidelity across all media formats.

### 2. High-Speed Inference (YOLOv8n)
Utilizes the Ultralytics YOLOv8 Nano (`yolov8n.pt`) model to achieve real-time, high-FPS processing speeds without sacrificing spatial accuracy, making it viable for edge-device deployment.

### 3. Automated Telemetry & HTML Reporting
The system does not just process video; it acts as an analytical data logger. Every processed frame logs:
* Number of persons detected.
* Exact spatial coordinates (`Box(X1, Y1, X2, Y2)`).
* Algorithmic confidence scores.
Upon completion, the pipeline automatically generates `detection_report.html`, a stylized dashboard allowing stakeholders to review the detection statistics (Total detections, Average per frame, Overall detection rate) without needing to watch the raw video.

---

## 📊 Pipeline Architecture
1. **Input Ingestion:** Loads high-resolution video assets.
2. **Inference Engine:** YOLOv8 scans frame-by-frame for the "Person" class.
3. **Post-Processing:** Applies 4K-scaled annotations using OpenCV.
4. **Data Aggregation:** Calculates total detections, averages, and rates.
5. **Output Generation:** Exports the annotated `.mp4` video and the `detection_report.html` dashboard.

---

## 🚀 How to Run the Project

**1. Clone the repository**
```bash
git clone [https://github.com/aansikkaw/Person-Detection-Model-in-4K.git](https://github.com/aansikkaw/Person-Detection-Model-in-4K.git)
cd Person-Detection-Model-in-4K
