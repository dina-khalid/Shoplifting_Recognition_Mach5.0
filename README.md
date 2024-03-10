# Shoplifting Recognition Machathon 5.00 
1st place final leader-board Machathon 5.00 solution

## Overview

This repository contains the implementation and fine-tuning process of the VideoMAE model for shoplifting recognition. VideoMAE is a self-supervised video pre-training method utilizing masked autoencoders to learn data-efficient video representations. The model is fine-tuned on a specific shoplifting dataset to enhance its ability to detect instances of shoplifting behavior in videos.

## Datasets Used

1. **[Machathon Dataset](https://drive.google.com/drive/folders/1LbV_sHKRhJ1LYq-UUmPkFgM-MEp9qURO)**
2. **[Shoplifting Dataset (2022) - CV Laboratory MNNIT Allahabad](https://data.mendeley.com/datasets/r3yjf35hzr/2)**

## Fine-Tuned Model: VideoMAE

The VideoMAE model is fine-tuned using high-ratio video masking, which improves video reconstruction performance and generalization on small datasets. This approach demonstrates impressive results without the need for additional data, making VideoMAE a data-efficient learner for self-supervised video pre-training.

## Fine-Tuning Process

### 1. Preparing Shoplifting Data

Collect or curate a specific dataset of videos containing instances of shoplifting behavior for fine-tuning.

### 2. Fine-Tuning the Video Model

- Initialize the pre-trained VideoMAE model with its weights.
- Replace or modify the final classification layer(s) to match the number of shoplifting classes in your dataset.

### 3. Addressing Challenges

To address overfitting on the "no_lifting" class, data augmentation techniques are applied during the fine-tuning process.

### 4. Video Preprocessing via YOLOv5

Utilize YOLOv5 to detect "person" objects in videos. Extract bounding box coordinates and class labels for the detected objects. Note: YOLOv5 may often misclassify objects.

![image](https://github.com/dina-khalid/Shoplifting_Recognition_Mach5.0/assets/69371669/c195034d-cfb5-463a-b9bd-61efdc246851)


### 5. Video Preprocessing via YOLOv8

Apply a blur effect to the background around the detected "person" objects. Create masks for each person, bounding box, and blend them with the original frame using Gaussian blur.

![image](https://github.com/dina-khalid/Shoplifting_Recognition_Mach5.0/assets/69371669/0029eac1-4bdc-47e7-89c0-ff78438eecd0)

### 6. Fine-Tuning VideoMAE with Preprocessing

Apply YOLOv8 preprocessing to the shoplifting dataset. Use the preprocessed data as input to fine-tune the VideoMAE model for improved shoplifting detection.


### 7. Training Details

- Used 4 epochs.
- Sampled each video to 16 frames per video.


## Leaderboard
My team Wandenreich meaning made it to the highest score on the final leaderboard 

![WhatsApp Image 2024-03-10 at 10 33 43 PM](https://github.com/dina-khalid/Shoplifting_Recognition_Mach5.0/assets/69371669/538b7f9f-10fd-4671-b338-0af27e8b75fd)


## Team Members

<div align="center">

[![Dina Khalid](https://github.com/dina-khalid.png?size=100)](https://github.com/dina-khalid) [![Mina Safwat](https://github.com/mena5800.png?size=100)](https://github.com/mena5800) [![Omnia Sayed](https://github.com/omniaSayed.png?size=100)](https://github.com/omniaSayed)

[Dina Khalid](https://github.com/dina-khalid) | [Mina Safwat](https://github.com/mena5800) | [Omnia Sayed](https://github.com/omniaSayed)

</div>



