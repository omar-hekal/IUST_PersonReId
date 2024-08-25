# IUST_PersonReId Dataset   <p align="left">   [![per](https://img.shields.io/badge/lang-per-yellow.svg)](https://github.com/ComputerVisionIUST/IUST_PersonReId/blob/main/README.per.md) </p>

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

![356862965-67af25b9-d743-44a2-96f3-b51eed0e8a08](https://github.com/user-attachments/assets/490f0d3e-db4a-47a0-a79b-5e93135f5510)


### Update...
Currently, more than 270,000 frames containing 32,668 annotation bounding boxes with 3,205 identities have been annotated among the raw videos. Among them, 1878 identities belong to people who were seen in 2 or more cameras, and 1327 identities belong to people who were present in the range of only 1 camera. Also, in terms of gender, this data set includes 50 female identities and 20 male identities. The IRUST dataset has four salient features::

First, it uses the [YOLOE](https://github.com/PaddlePaddle/PaddleDetection/blob/release/2.7/deploy/pipeline/docs/tutorials/pphuman_mot_en.md) model trained on the [crowdhuman](https://www.crowdhuman.org/) dataset as pedestrian tracking.

Second, since the above AI models may not be efficient enough (such as not detecting when entering and exiting the camera range, not detecting veiled people, not detecting pedestrian equipment, or switching IDs, etc.), human annotators change the annotation. they give. It is made in such a way that the least possible errors occur in the training of the models in terms of the dataset.

Third, a basic person reidentification model was implemented using [Swin Transformer](https://github.com/layumi/Person_reID_baseline_pytorch) on the cropped images of the frames.

Fourth, human observers were used to correct the re-identification errors of people in different cameras along with the temporal re-identification algorithm. This work is done in the framework of a developed application specific to the subject of re-identification.

To know the details of annotation rules, you can refer to the following [link](https://docs.google.com/document/d/1Upnm1nJ9e8Jn3odAjlbICwgNXtRzPghF7wl5_eQRcdo/edit?usp=sharing)


In the demo below, the reason for the inadequacy of using artificial intelligence models is obvious


<p align="center">
  <img src="https://github.com/user-attachments/assets/ae6eadc9-dbe5-46c7-bf1a-0733830069d3" alt="animated" />
</p>

<p align="center">
  <img src="https://github.com/user-attachments/assets/11399f88-e4a1-4f0b-80ea-75225e1ac246" alt="animated" />
</p>



Also, this dataset includes images of people who are not in front of the camera with the same clothes.
Pay attention to the image below, this identity was present in several frames with a tent and in the rest of the frames with a mantle.


![image](https://github.com/user-attachments/assets/03590215-9ce6-42d7-8e50-36a6baea79d5)



### Download dataset
You can download the dataset package from [here](https://zaya.io/cnzrl)

### Bboxes naming convention

For example: C1_F6595_ID10.jpeg

"C1" is the camera number at that particular location.

"F6595" is the frame number of that person in the partitioned movie.

"ID10" is the identity number of the person in the provided collection.


-----------------------------------------------------------------------------------------------------------------------------------------
