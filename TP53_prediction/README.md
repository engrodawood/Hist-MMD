# TP-53 gene point mutation status predicition

## Introduction
We assessed the significance of the proposed MMD kernels in predicting the mutation status of TP-53. TP-53 is a tumor supressor gene that has great signficance for breast cancer as it can found in 20–40% of all breast cancer cases while also being a determinant of underlying cancer pathways and treatment options. To do this we used a binary class Support Vector Machine (SVM) with a precomputed kernel. The models performance was measured by using AUC-ROC with the 95% Confidence Interval (CI).

## Usage
To perform this the $652 \times 652$ distance matrix and its correspsoning slide IDs located at `data/MMD_matrix/D_652_blur_10.npy` and `data/MMD_matrix/slide_IDs_652.npy` respectively. You can also use your own distance matrix by using `MMD_distance_matrix_generator`.

To generate and validate an SVM for TP-53 gene point mutation status predicition use the IPython Notebook file `TP52_prediction/TP53_prediction.ipynb`.
