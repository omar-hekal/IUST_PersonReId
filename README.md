# IUST_PersonReId Dataset   <p align="left">  [![per](https://img.shields.io/badge/lang-tr-red.svg)](https://https://github.com/ComputerVisionIUST/IUST_PersonReId/edit/main/README.md)  [![tr](https://img.shields.io/badge/lang-pr-yellow.svg)](https://github.com/aytakg/reid/blob/main/README.pr.md) </p>

![1](https://github.com/IRIUST/Iranians_Reid_dataset/assets/141324225/782122d5-235a-4314-9d81-7eceec56c960)

### About dataset

The IRIUST dataset is different from the international datasets and has been prepared according to the culture and environment of Iran. In this dataset, it has been attempted to capture raw data footage from locations and conditions that maintain a range of challenges (film quality, lighting, diversity, camera angle, etc.) in the dataset. Field-of-view overlap exists among different cameras. Therefore, this dataset can be a good representative of the real world dataset.
These videos were recorded by cameras with different resolution quality in places such as Iran University of Science and Technology, Al-Aima Mosque, Arbaeen procession, local fruit shop and supermarket in Tehran, the details of which are given separately in the table below.

| Location  | Cameras | Total hours | Resolution |Num of day|
| ------  | :---:  | :---:  | :---:  | :---:  |
| Iran University of Science and Technology  | 17 | 383 h| Variable| 5|
| Al-Aima Mosque | 5 | 40 h| 960×1080 | 2|
| local fruit shop | 7 | 38 h | 944×1080 | 1 |
| local supermarket | 6 | 124 h | 1280×1944  | 4 |
| Arbaeen procession | 2 | 3 h | 1280×720 | 5 |

The statistical comparison of the world's famous labeled datasets with our dataset is given in the following table:

| Dataset | Location  | ID-multi camera | ID-single camera | scenes | images |
| ----- | ------  | :---:  | :---:  | :---:  | :---:  |
| ScoreNet  | Football leagues | 243432 | - | -| 340993|
| MSMT17  | University campus | 4101 | - | 15| 126441 |
| Duke | Duke University campus | 1413 | 439 | 8 | 466261 |
| MARS | Tsinghua University campus | 1261 | - | 6  | 1191003 |
| Market1501 | Supermarket in Tsinghua University | 1501 | - | 6 | 32217 |
| IUST | Different places inside Iran | 1878 | 1327 | 19 | - |



The number of IDs that have been synchronized in several cameras have been viewed:
<p align="center"><img src="![_Labeled Data](https://github.com/user-attachments/assets/67226f29-5ab6-4e36-ac66-b910b48faad1)" width="750"/></p>
![_Labeled Data](https://github.com/user-attachments/assets/67af25b9-d743-44a2-96f3-b51eed0e8a08)


### Update...
Currently, more than 270,000 frames containing 32,668 annotation bounding boxes with 3,205 identities have been annotated among the raw videos. Among them, 1878 identities belong to people who were seen in 2 or more cameras, and 1327 identities belong to people who were present in the range of only 1 camera. Also, in terms of gender, this data set includes 50 female identities and 20 male identities. The IRUST dataset has four salient features::

First, it uses the [YOLOE](https://github.com/PaddlePaddle/PaddleDetection/blob/release/2.7/deploy/pipeline/docs/tutorials/pphuman_mot_en.md) model trained on the [crowdhuman](https://www.crowdhuman.org/) dataset as pedestrian tracking.

Second, since the above AI models may not be efficient enough (such as not detecting when entering and exiting the camera range, not detecting veiled people, not detecting pedestrian equipment, or switching IDs, etc.), human annotators change the annotation. they give. It is made in such a way that the least possible errors occur in the training of the models in terms of the dataset.

Third, a basic person reidentification model was implemented using [Swin Transformer](https://github.com/layumi/Person_reID_baseline_pytorch) on the cropped images of the frames.

Fourth, human observers were used to correct the re-identification errors of people in different cameras along with the temporal re-identification algorithm. This work is done in the framework of a developed application specific to the subject of re-identification.




[![Watch the video]()](https://github.com/user-attachments/assets/ef987d49-9f29-423d-a4c4-b7f0a9b2b612)

https://github.com/user-attachments/assets/aa5ee71a-a359-484e-8e5b-da43611097a5




To know the details of annotation rules, you can refer to the following [link](https://docs.google.com/document/d/1rZ8E1QVWvn_c9F-WZDP7kzvAkSqddh-mRWyCYfB-iZY/edit?pli=1)


In the demo below, the reason for the inadequacy of using artificial intelligence models is obvious
https://github.com/IRIUST/Iranians_Reid_dataset/assets/141324225/fde81249-5d40-4a11-9be4-2117e11c2896

Also, this dataset includes images of people who are not in front of the camera with the same clothes.
Pay attention to the image below, this identity was present in several frames with a tent and in the rest of the frames with a mantle.


! [2] (https://github.com/IRIUST/Iranians_Reid_dataset/assets/141324225/ec09a671-b130-408a-aaa5-c405d2d81c08)




### Download dataset
You can download the dataset package from [here](https://drive.google.com/file/d/1BoBmL1FtYON4coItUbvBFWlS4vUw8Qz_/view?usp=sharing)

### Bboxes naming convention

For example: C1_F6595_ID10.jpeg

"C1" is the camera number at that particular location.

"F6595" is the frame number of that person in the partitioned movie.

"ID10" is the identity number of the person in the provided collection.
