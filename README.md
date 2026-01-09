# AI-Based Wildlife Species Detection 

This project implements an **AI-based wildlife species detection system** using **YOLOv8** and **Roboflow**.  
The goal is to automatically detect and classify wildlife species from images, which is especially useful for **camera trap analysis, wildlife monitoring, and conservation research**.

---

## 📌 Project Overview

- **Task**: Object Detection (Multi-class)
- **Model**: YOLOv8
- **Framework**: Ultralytics YOLO
- **Dataset Tool**: Roboflow
- **Use Case**: Wildlife monitoring, conservation, and research
- **Project Type**: Final Year / Research / Resume Project

---

## 🗂 Dataset

- The dataset was created and annotated using **Roboflow**.
- It contains **multiple wildlife species and humans**.
- Images are split into **train / validation / test** sets.

⚠️ **Note**:  
Due to GitHub size limits, raw images are not included in this repository.  
Only the dataset structure and labels are provided as `dataset.zip`.

📥 **Dataset Source (Roboflow)**  

The dataset was created and annotated using **Roboflow**.  
Due to privacy and size constraints, the dataset is kept **private** on Roboflow.

- Raw images are hosted securely on Roboflow
- This repository includes only the dataset structure and labels (`dataset.zip`)
- The full dataset can be programmatically downloaded during training using the Roboflow API (with an API key)


---

## 🧠 Model Details

- **Architecture**: YOLOv8
- **Training Platform**: Roboflow Training + Ultralytics
- **Checkpoint Type**: Object Detection (Fast)

### 📊 Performance Metrics
| Metric | Value |
|------|------|
| mAP@50 | **82.7%** |
| Precision | **84.0%** |
| Recall | **77.2%** |

---

## ⚙️ Setup Instructions

### 1️⃣ Clone the Repository

git clone https://github.com/Rupam160/AI-Based-Wildlife-Species-Detection.git
cd AI-Based-Wildlife-Species-Detection

🏋️ Model Training (YOLOv8)

Training is done using Google Colab or a local GPU.

Install Dependencies
pip install ultralytics roboflow

Download Dataset from Roboflow
from roboflow import Roboflow

rf = Roboflow(api_key="YOUR_API_KEY")
project = rf.workspace("rupam").project("humans-and-animals-detection-v2vzd")
dataset = project.version(1).download("yolov8")

Train the Model
from ultralytics import YOLO

model = YOLO("yolov8n.pt")
model.train(data="data.yaml", epochs=50, imgsz=640)

🔍 Inference
Image Inference
python inference/predict_image.py --image sample.jpg

Video Inference
python inference/predict_video.py --video input.mp4

🎯 Applications

Wildlife population monitoring

Camera trap image analysis

Forest surveillance

Human–animal interaction detection

Conservation research

🔮 Future Work

Deploy as a Streamlit web application

Add real-time video inference

Improve accuracy with data augmentation

Deploy as an API using FastAPI

👤 Author

Rupam Barat
B.Tech – Computer Science & Engineering
Final Year Project

📜 License

This project is released for academic and research purposes.
