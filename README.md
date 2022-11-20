# Maximum Mean Discrepancy Kernels For Predictive And Prognostic Modeling Of Whole Slide Images
### Piotr Keller*, Muhammad Dawood* and Fayyaz ul Amir Afsar Minhas
### Tissue Image Analytics Center, University of Warwick, United Kingdom

This repository contains the code for the following manuscript:

Maximum Mean Discrepancy Kernels for Predictive and Prognostic Modeling of Whole Slide Images, submitted to IEEE International Symposium on Biomedical Imaging (ISBI) 2023 for review.

## Introduction
How similar are two images? In computational pathology, where Whole Slide Images (WSIs) of digitally scanned tissue samples from patients can be multi-gigapixels in size, determination of degree of similarity between two WSIs is a challenging task with a number of practical applications. In this work, we explore a novel strategy based on kernelized Maximum Mean Discrepancy (MMD) analysis for determination of pairwise similarity between WSIs. The proposed approach works by calculating MMD between two WSIs using kernels over deep features of image patches. This allows representation of an entire dataset of WSIs as a kernel matrix for WSI level clustering, weakly-supervised prediction of TP-53 mutation status in breast cancer patients from their routine WSIs as well as survival analysis with state of the art prediction performance. We believe that this work will open up further avenues for application of WSI-level kernels for predictive and prognostic tasks in computational pathology.

<img src="workflow.png" alt="Block Diagram"/>

## Usage
### Step 1. Data download
Download the FFPE whole slide images from GDC portal (https://portal.gdc.cancer.gov/) for breast carcinoma (TCGA-BRCA).

Download corresponding gene point mutation and Disease Specific Survival from cBioPortal (https://www.cbioportal.org/).
### Step 2. Data processing
Using the code under `code_data_processing` to perform

- Slide selection: select high quality WSIs from the original dataset 
- Tile extraction: extract 512x512 tiles from the large WSI at a spatial resolution of 0.50 microns-per-pixel
- Patches capturing less that 40% of informative tissue are discarded
- Stain normalization
- Feature extraction: extract a feature vector for each tile using SuffleNet pretrained on ImageNet


Details can be found in the paper and code_data_processing.
### Step 3. MMD Kernel generation for 1024-dimensional feature representations of 652 and 1052 TCGA-BRCA slides 

Using the code under `MMD_distance_matrix_generator` to generate an $N \times N$ distance matrix using MMD where $N$ is the number of WSIs in a dataset.

Details can be found in the paper and MMD_distance_matrix_generator.

### Step 4. SVM model generation and validation for TP-53 point mutation status prediciton

Using the code under `TP53_prediction` to generate a Support Vector Machine (SVM) with a predefined kernel (generated from the 652 distance matrix from Step 3.) to predict TP-53 point status mutation for breast patients.

Details can be found in the paper and TP53_prediction.

### Step 5. SVM model generation and validation for kernalized survival analysis

Using the code under `survival_analysis` to generate a Support Vector Machine (SVM) with a predefined kernel (generated from the 1052 distance matrix from Step 3.) to predict survival for breast patients.

Details can be found in the paper and survival_analysis.

## Note

Some intermediate data are put into the folder `data`.
