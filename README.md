# sa7495_mlLab4
# Name: Shivek Aggarwal  
# Net ID: sa7495

## Table of Contents
1. Outline
2. System Specifications
3. Repository Structure
4. Installation and Operation Guide
5. Data

## Outline
This repository contains the code for a new system designed to detect hidden vulnerabilities, or backdoors, within neural networks. This project aims to bolster security within neural networks, especially those trained on the YouTube Face dataset, by creating an advanced model called GoodNet. GoodNet is specifically crafted to distinguish between regular and compromised inputs, effectively categorizing them into distinct groups.

## System Specifications
Environment: MacBook equipped with M1 chip
Interface: Google Colab Pro

## Repository Structure
sa7495_mlLab4: Colab Notebook
eval.py: Script to assess model accuracy.
sa7495_mlLab4Report : Report

## Installation and Operation Guide
Download the repository to your system.
Run Google Colab Notebook and upload data to Google Drive. (Refer below the data section for more information)

## Data
1.  Download the validation and test datasets from  [here](https://drive.google.com/drive/folders/1Rs68uH8Xqa4j6UxG53wzD0uyI8347dSq?usp=sharing) and upload them to Google Drive under
     bd/ and cl/ and sunglasses_bd_net.h5
3.  The dataset contains images from the YouTube Aligned Face Dataset. We retrieved 1283 individuals and split them into validation and test datasets.
4.  bd_valid.h5 and bd_test.h5 contains validation and test images with sunglasses trigger respectively, that activates the backdoor for bd_net.h5.

