# Dynamic-Threshold-for-Image-Retrieval
Code for 'Dynamic Threshold for Image Retrieval' (CSoNet 2024). We propose a dynamic threshold method for content-based image retrieval that adapts to each image gallery, enhancing accuracy over static thresholds using CLIP and FAISS.

Abstract
--------

This repository contains the implementation of the paper "Dynamic Threshold for Image Retrieval," accepted at CSoNet 2024. The paper introduces a dynamic threshold method for content-based image retrieval (CBIR) that adapts the retrieval threshold for each image gallery based on the distribution of similar images in the feature space. Unlike static thresholds, which struggle to accommodate varying query characteristics, our approach leverages the CLIP model for feature extraction and FAISS for efficient similarity search to achieve superior retrieval accuracy. Evaluations on the ROxford and LogoSearch datasets demonstrate significant improvements over traditional static threshold methods.

* * * * *
Colab Notebook
-------------------
Access the notebook here:  
[**Colab Notebook Link**](https://colab.research.google.com/drive/1GTt0Qmzv04xooUJC4zgbsGS_P1tc13JS?usp=sharing)  

The notebook includes everything you need:
- Feature extraction using CLIP
- Distance calculation with FAISS
- Dynamic threshold determination
- Evaluation on the ROxford dataset
* * * * *

Method Overview
---------------

![main](https://github.com/user-attachments/assets/34c97c32-9fc8-4f08-bdd4-70280a03759e)

The proposed method enhances CBIR through a dynamic thresholding approach. Here's how it works:

1.  **Feature Extraction**:\
    The CLIP model encodes both query and gallery images into a 1024-dimensional latent space, capturing rich semantic representations.
2.  **Distance Calculation**:\
    FAISS computes Euclidean distances between the latent vectors of the query and gallery images, enabling efficient similarity search.
3.  **Dynamic Threshold Determination**:
    -   For each gallery, the mean distance to its top n n n most similar images is calculated.
    -   A global mean distance is computed across all galleries.
    -   The dynamic threshold for each gallery is derived by adjusting a static threshold with a weighted difference between the gallery's mean distance and the global mean.
4.  **Retrieval**:\
    Images are retrieved if their distance to the query falls below the gallery-specific dynamic threshold, ensuring adaptability to diverse gallery characteristics.

This approach improves retrieval precision by tailoring the threshold to the unique properties of each gallery.




* * * * *

Results
-------

The dynamic thresholding method was evaluated against a static threshold baseline on the ROxford and LogoSearch datasets. Key improvements in macro F1 scores include:

-   **ROxford (medium)**: 12.4% improvement (from 0.302 to 0.3394)
-   **ROxford (hard)**: 6.41% improvement (from 0.2620 to 0.2788)
-   **LogoSearch**: 2.72% improvement (from 0.9488 to 0.9746)

These gains highlight the method's ability to enhance CBIR performance across datasets of varying complexity.

![image](https://github.com/user-attachments/assets/e86f726a-e261-42ae-a5e9-790e8e6e2f7b)
![image](https://github.com/user-attachments/assets/e52da62d-51ee-42ec-8c6f-37a912487090)



* * * * *

Citation
--------

If you use this code in your research, please cite our paper:

`waitting`

* * * * *

License
-------

This project is released under the MIT License. See the <LICENSE> file for details.

* * * * *
