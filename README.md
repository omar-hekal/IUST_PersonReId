# IUST_PersonReId Dataset  
<p align="left">  
  [![per](https://img.shields.io/badge/lang-per-yellow.svg)](https://github.com/ComputerVisionIUST/IUST_PersonReId/blob/main/README.per.md)  
</p>

![Dataset Overview](https://github.com/IRIUST/Iranians_Reid_dataset/assets/141324225/782122d5-235a-4314-9d81-7eceec56c960)

## About the Dataset

The **IRIUST** dataset is distinct from international datasets, designed specifically to reflect the cultural and environmental context of Iran. It captures raw video footage from various locations under diverse conditions (e.g., film quality, lighting, camera angles), making it a valuable representation of real-world scenarios. The dataset includes overlapping fields of view from multiple cameras.

### Recorded Locations
The videos were recorded in the following locations, with details summarized in the table below:

| Location                                      | Cameras | Total Hours | Resolution   | Number of Days |
|-----------------------------------------------|---------|-------------|--------------|----------------|
| Iran University of Science and Technology     | 17      | 383         | Variable     | 5              |
| Al-Aima Mosque                               | 5       | 40          | 960×1080     | 2              |
| Local Fruit Shop                              | 7       | 38          | 944×1080     | 1              |
| Local Supermarket                             | 6       | 124         | 1280×1944    | 4              |
| Arbaeen Procession                            | 2       | 3           | 1280×720     | 5              |

### Comparison with Other Datasets
The following table compares our dataset with some well-known labeled datasets globally:

| Dataset    | Location                | ID (Multi Camera) | ID (Single Camera) | Scenes | Images   |
|------------|-------------------------|--------------------|---------------------|--------|----------|
| ScoreNet   | Football Leagues        | 243432             | -                   | -      | 340993   |
| MSMT17     | University Campus       | 4101               | -                   | 15     | 126441   |
| Duke       | Duke University Campus   | 1413               | 439                 | 8      | 466261   |
| MARS       | Tsinghua University     | 1261               | -                   | 6      | 1191003  |
| Market1501 | Supermarket, Tsinghua   | 1501               | -                   | 6      | 32217    |
| **IUST**   | Various Locations in Iran| **1878**           | **1327**            | 19     | -        |

### Annotation Statistics
As of now, the dataset contains over 270,000 frames with 32,668 annotated bounding boxes across 3,205 identities. Notably, 1,878 identities appear in multiple cameras, while 1,327 identities are unique to a single camera. Gender distribution includes 50 female and 20 male identities.

## Key Features

1. **Pedestrian Tracking**: Utilizes the [YOLOE](https://github.com/PaddlePaddle/PaddleDetection/blob/release/2.7/deploy/pipeline/docs/tutorials/pphuman_mot_en.md) model trained on the [CrowdHuman](https://www.crowdhuman.org/) dataset.
  
2. **Human Annotations**: Human annotators refine the dataset to minimize errors in model training, addressing limitations of AI detection (e.g., missed detections, veiled individuals).

3. **Re-identification Model**: A basic person re-identification model was developed using [Swin Transformer](https://github.com/layumi/Person_reID_baseline_pytorch) on cropped images.

4. **Error Correction**: Human observers correct re-identification errors across different cameras using a temporal re-identification algorithm within a dedicated application.

For detailed annotation rules, refer to the [annotation documentation](https://docs.google.com/document/d/1Upnm1nJ9e8Jn3odAjlbICwgNXtRzPghF7wl5_eQRcdo/edit?usp=sharing).

### Labeled Data Overview
<p align="center">
  <img src="https://github.com/user-attachments/assets/67226f29-5ab6-4e36-ac66-b910b48faad1" width="750" alt="Labeled Data Overview" />
</p>

### Demonstration of AI Limitations
The following animations illustrate the challenges of relying solely on artificial intelligence models:



<div align="center">
  <img src="https://github.com/user-attachments/assets/ae6eadc9-dbe5-46c7-bf1a-0733830069d3" alt="AI Detection Challenges" width="400" height="300" style="margin: 10px; border: 4px solid #007BFF; border-radius: 8px; box-shadow: 0 4px 10px rgba(0, 0, 0, 0.2);" />
  <img src="https://github.com/user-attachments/assets/11399f88-e4a1-4f0b-80ea-75225e1ac246" alt="AI Detection Challenges" width="400" height="300" style="margin: 10px; border: 4px solid #007BFF; border-radius: 8px; box-shadow: 0 4px 10px rgba(0, 0, 0, 0.2);" />
</div>

### Unique Identifications
The dataset also includes images of individuals wearing the same clothing at different times. For example, one identity was seen in various frames wearing a tent and later in a mantle.

![Identity Variation](https://github.com/user-attachments/assets/03590215-9ce6-42d7-8e50-36a6baea79d5)

## Download the Dataset
You can download the dataset package from [this link](https://zaya.io/cnzrl).

### Bounding Box Naming Convention
The naming convention for bounding boxes is as follows: **C1_F6595_ID10.jpeg**

- **C1**: Camera number at the specific location.
- **F6595**: Frame number of that individual in the partitioned video.
- **ID10**: Identity number of the individual in the dataset.

---
