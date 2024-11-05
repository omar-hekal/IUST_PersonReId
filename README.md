# IUST_PersonReID Dataset  
<div align="left">
 
[![per](https://img.shields.io/badge/Language-Persian-orange.svg)](https://github.com/ComputerVisionIUST/IUST_PersonReId/blob/main/README.per.md)  

</div>

![Dataset Overview](https://github.com/IRIUST/Iranians_Reid_dataset/assets/141324225/782122d5-235a-4314-9d81-7eceec56c960)

## About the Dataset

The **IUST_PersonReID** dataset is distinct from international datasets, designed specifically to reflect the cultural and environmental context of Iran. It captures raw video footage from various locations under diverse conditions (e.g., film quality, lighting, camera angles), making it a valuable representation of real-world scenarios. The dataset includes overlapping fields of view from multiple cameras.

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
| **IUST_PersonReID**   | Various Locations in Iran| **1878**           | **1327**            | 19     | -        |

### Annotation Statistics
As of now, the dataset contains over 270,000 frames with 32,668 annotated bounding boxes across 3,205 identities. Notably, 1,878 identities appear in multiple cameras, while 1,327 identities are unique to a single camera. Gender distribution includes 50 female and 20 male identities.
<p align="center">
  <img src="https://github.com/user-attachments/assets/b94e5b53-8a8f-433c-a562-87f6d6af7381" width="500" alt="Number of IDs per Camera numbers" />
</p>


## Key Features

1. **Pedestrian Tracking**: Utilizes the [YOLOE](https://github.com/PaddlePaddle/PaddleDetection/blob/release/2.7/deploy/pipeline/docs/tutorials/pphuman_mot_en.md) model trained on the [CrowdHuman](https://www.crowdhuman.org/) dataset.
  
2. **Human Annotations**: Human annotators refine the dataset to minimize errors in model training, addressing limitations of AI detection (e.g., missed detections, veiled individuals).

3. **Re-identification Model**: A basic person re-identification model was developed using [Swin Transformer](https://github.com/layumi/Person_reID_baseline_pytorch) on cropped images.

4. **Error Correction**: Human observers correct re-identification errors across different cameras using a temporal re-identification algorithm within a dedicated application.

For detailed annotation rules, refer to the [annotation documentation](https://docs.google.com/document/d/1Upnm1nJ9e8Jn3odAjlbICwgNXtRzPghF7wl5_eQRcdo/edit?usp=sharing).

### Demonstration of AI Limitations
The following video illustrate the challenges of relying solely on artificial intelligence models:

https://github.com/user-attachments/assets/4cef8880-6f00-43e4-a52d-eb3f8657c31b

### Unique Identifications
The dataset also includes images of individuals wearing the same clothing at different times. For example, one identity was seen in various frames wearing a tent and later in a mantle.

![Identity Variation](https://github.com/user-attachments/assets/03590215-9ce6-42d7-8e50-36a6ba9d5)

## Download the Dataset

You can download the dataset package from [Google Drive](https://zaya.io/iust_personreid).

### Bounding Box Naming Convention

The **IUST_PersonReID** dataset adopts a naming convention identical to that of the Market-1501 dataset. The image naming format is structured as follows:

```
<personID>_<cameraID>_<sequenceID>_<frameID>.<extension>
```

#### Components Breakdown

1. **personID**: A unique identifier for each individual in the dataset, ranging from `0001` to the total number of identified persons.

2. **cameraID**: A single-digit identifier indicating the camera that captured the image. This ranges from `1` to the total number of cameras used in the dataset.

3. **sequenceID**: In the **IUST_PersonReID** dataset, this field is often fixed as `s1`, as it does not vary significantly.

4. **frameID**: A unique number that indicates the frame in which the person appears. This is crucial for distinguishing images captured in rapid succession of the same person and camera.

5. **extension**: The file format of the image, typically `.jpg`.

#### Example Filename

A typical filename in the **IUST_PersonReID** dataset might look like this:

```
0001_c1_s1_000151.jpg
```

#### Interpretation:

- **0001**: `personID` = `0001`
- **c1**: `cameraID` = `1`
- **s1**: `sequenceID` = `1` (often static in this dataset)
- **000151**: `frameID` = `151`

Each image represents a cropped bounding box of a pedestrian captured by one of the cameras in a real-world setting. The `personID` and `cameraID` are particularly important for person re-identification tasks, where the goal is to match images of the same individual across different camera views.

---
