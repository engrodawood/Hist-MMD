# MMD distance matrix generator

## Introduction
We generate a distance matrix using MMD as the distnace metric for two datasets. For all nodes in each WSI we use an 1024-dimensional feature representation by extracting the latent representation of the second-last fully connected layer of an ImageNet pretrained SuffleNet. This feature representation was generated for all WSIs used for TP53 gene point mutation prediciton (https://drive.google.com/file/d/1Q4KvkxSl8cimAZXxxmvU1WcdI_2Wa1bg/view?usp=sharing) and survival analysis (https://drive.google.com/file/d/1VhFjyFtiu4UwnbImGl-0iLJPOmp1FQ5c/view?usp=sharing).

## Usage
To generate these matrices use the IPython Notebook file `MMD_distance_matrix_generator/distance_matrix_generator.ipynb`.

To then visualise the generated distance matrix use `MMD_distance_matrix_generator/distance_matrix_visualisation.ipynb`
