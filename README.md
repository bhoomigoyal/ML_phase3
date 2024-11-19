
# Dynamic Window Swin Transformer

This repository contains the implementation of our model for **Dynamic Window Swin Transformer**. The model addresses compression artifacts in images and enhances their visual quality using a content-adaptive approach.

---

## Table of Contents
1. [Introduction](#introduction)
2. [Features](#features)
3. [Installation](#installation)
4. [Dataset Preparation](#dataset-preparation)
5. [Training the Model](#training-the-model)

---

## Introduction

Modern image compression standards like VVC introduce complex artifacts (blocking, blurring, ringing). Our method leverages dynamic window partitioning, mixed attention mechanisms, and locally enhanced networks to restore high-quality images.

### Key Highlights:
- Utilizes **SwinIR-based architecture** with improvements like content-adaptive dynamic windows.
- Achieves **state-of-the-art performance** in reducing compression artifacts.
- Supports **multi-scale super-resolution** (x2, x3, x4).

---

## Features

- **Dynamic Window Partitioning** for multi-scale dependencies.
- **Mixed Attention Module (AMAM)** for adaptive feature weighting.
- **Flexible Locally-Enhanced Feed-Forward Network (FLeFF)** for refining local textures.

---

## Installation

### Clone the Repository
Run the following commands:
<br><br>
git clone https://github.com/cszn/KAIR.git <br>
%cd KAIR


---

## Dataset Preparation

We use the **DIV2K Dataset** for training the model. Follow these steps to download and organize the dataset:

### 1. Create Necessary Directories
Run the following commands:
<br><br>
!mkdir -p trainsets/trainH/HR <br>
!mkdir -p trainsets/trainH/LR_bicubic/X2/ <br>
!mkdir -p trainsets/trainH/LR_bicubic/X3/ <br>
!mkdir -p trainsets/trainH/LR_bicubic/X4/ <br>


### 2. Download DIV2K Training Set
Run the following commands:
<br><br>
!wget https://data.vision.ee.ethz.ch/cvl/DIV2K/DIV2K_train_HR.zip <br>
!wget https://data.vision.ee.ethz.ch/cvl/DIV2K/DIV2K_train_LR_bicubic_X2.zip <br>
!wget https://data.vision.ee.ethz.ch/cvl/DIV2K/DIV2K_train_LR_bicubic_X3.zip <br>
!wget https://data.vision.ee.ethz.ch/cvl/DIV2K/DIV2K_train_LR_bicubic_X4.zip <br>


### 3. Extract and Organize the Data
Run the following commands:
<br><br>
!unzip DIV2K_train_HR.zip -d trainsets/trainH/HR/ <br>
!unzip DIV2K_train_LR_bicubic_X2.zip -d trainsets/trainH/LR_bicubic/X2/ <br>
!unzip DIV2K_train_LR_bicubic_X3.zip -d trainsets/trainH/LR_bicubic/X3/ <br>
!unzip DIV2K_train_LR_bicubic_X4.zip -d trainsets/trainH/LR_bicubic/X4/ <br>


---

## Install Required Packages

Ensure Python and pip are installed. Install the necessary dependencies: <br>

!pip install -r requirements.txt


---

## Training the Model

### Run the Training Script
To start training the model for super-resolution, use the following command: <br>

!python main_train_psnr.py --opt options/swinir/train_swinir_sr_classical.json


### Training Details:
- **Architecture**: SwinIR-based with dynamic enhancements.
- **Training Dataset**: DIV2K.

