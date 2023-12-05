# sa7495_mlLab4
# Name: Shivek Aggarwal  
# Net ID: sa7495

## Table of Contents
1. Outline
2. System Specifications
3. Repository Structure
4. Installation and Operation Guide
5. Data
6. Directory Structure
7. Procedure
8. Evaluating the Compromised Model
9. Contributions
10. Acknowledgements

## Outline
This repository contains the code for a new system designed to detect hidden vulnerabilities, or backdoors, within neural networks. The aim of this project is to bolster security within neural networks, especially those trained on the YouTube Face dataset, by creating an advanced model called GoodNet. GoodNet is specifically crafted to distinguish between regular and compromised inputs, effectively categorizing them into distinct groups.

## System Specifications
Environment: MacBook equipped with M1 chip
Interface: Google Colab Pro

## Repository Structure
sa7495_mlLab4: Colab Notebook.
model_evaluation.py: Script to assess model accuracy on untainted and compromised datasets.
Dataset/: Folder containing valid.h5 for validation and test.h5 for testing.

## Installation and Operation Guide
Download the repository to your system.
Set up a compatible Jupyter Notebook environment, ideally on a MacBook Pro with an M1 chip or an equivalent setup. Executing this project on Google colab is not recommended as it is very slow.
Install all required dependencies listed in requirements.txt.
Confirm the Dataset/ folder has the necessary data files.
Launch Notebook_PruneDefense.ipynb in Jupyter Notebook and run the cells in order.
For model evaluation, run model_evaluation.py, adjusting paths as needed for your environment.

## Data
1.  Download the validation and test datasets from  [here](https://drive.google.com/drive/folders/1Rs68uH8Xqa4j6UxG53wzD0uyI8347dSq?usp=sharing) and store them under  `lab4/data/`  directory.
2.  The dataset contains images from the YouTube Aligned Face Dataset. We retrieved 1283 individuals and split them into validation and test datasets.
3.  bd_valid.h5 and bd_test.h5 contains validation and test images with sunglasses trigger respectively, that activates the backdoor for bd_net.h5.

## Directory Structure
The project is organized as follows:

- `data/`: Contains datasets for validation and testing.
  - `cl/`: Clean datasets.
    - `valid.h5`: Clean validation data for defense design.
    - `test.h5`: Clean test data for BadNet evaluation.
  - `bd/`: Datasets with sunglasses-poisoned images.
    - `bd_valid.h5`: Validation data with backdoor trigger.
    - `bd_test.h5`: Test data with backdoor trigger.
- `models/`: Houses the neural network models.
  - `bd_net.h5`: The backdoored neural network model.
  - `bd_weights.h5`: Weight parameters for the model.
- `architecture.py`: Defines the neural network architecture.
- `eval.py`: Script for evaluating the model's performance.

## Procedure
This project's main aim was to enhance a machine learning model using a series of methodologies such as channel pruning, saving models based on accuracy metrics, evaluating potential vulnerabilities, and synthesizing an optimized hybrid model.

### Channel Pruning and Model Archiving
Our technique included reducing the conv_3 layer, guided by the average activation values from the final pooling stage in the validation dataset. We adopted a model-saving approach at accuracy decline benchmarks of 2%, 4%, and 10%, resulting in models named model_X=2.h5, model_X=4.h5, and model_X=10.h5 to reflect the corresponding accuracy decrease.

### Attack Vulnerability Analysis
A significant part of this project was to determine the model's vulnerability to attacks, particularly assessing the rate of successful attacks when the accuracy decreased by 30%. This evaluation revealed a notable vulnerability rate at approximately 6.95%.

### Constructing GoodNet
Our objective was to merge two versions of the model: the original, potentially compromised model ("BadNet") and its improved version post-pruning. This endeavor aimed to establish an advanced, resilient model dubbed "GoodNet."

### Implementation Overview
All programming code and execution steps are detailed in `MLSec_Lab4_mpj8687.ipynb`. This comprehensive notebook covers every aspect, from model development and pruning to evaluation, vulnerability analysis, and the fusion of models to form GoodNet.

## Evaluating the Compromised Model
For facial recognition, we utilized the DeepID network, a cutting-edge DNN architecture.

To assess the integrity of the compromised model, run `eval.py`:
python3 eval.py <clean validation data directory> <poisoned validation data directory> <model directory>

For instance:
python3 eval.py data/cl/valid.h5 data/bd/bd_valid.h5 models/bd_net.h5

This command will output metrics like 'Clean Classification Accuracy: 98.64%' and 'Attack Success Rate: 100%'.

## Contributions
Feedback and contributions are highly encouraged. For proposing changes or discussing new ideas, please initiate an issue or submit a pull request.

## Acknowledgements
Appreciation goes to the team behind CSAW-HackML-2020 for their foundational work and dataset provision.
Acknowledgement of NYU's support and resources in facilitating this resear
