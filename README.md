# Face Recognition with PCA and KNN Classifier

## Overview
This project focuses on recognizing human faces using Principal Component Analysis (PCA) for dimensionality reduction and a K-Nearest Neighbors (KNN) classifier for classification. The dataset used is "The Database of Faces" (formerly known as 'The ORL Database of Faces'), which contains face images of 40 subjects with different expressions, lighting conditions, and facial details. The main goal is to classify these subjects using the eigenfaces approach.

## Dataset
- **The Database of Faces**: Contains 400 grayscale images of 40 distinct subjects, each having 10 images. Variations include different lighting, facial expressions (e.g., smiling, open/closed eyes), and facial accessories (glasses/no glasses). Each image is of size 92x112 pixels, stored in PGM format.

## Workflow
1. **Data Matrix Generation**: 
   - The face images were flattened and stored in a matrix, where each row represents one image.
   - The matrix's dimensions are 400x10304 (400 images, 10304 features per image).

2. **PCA for Dimensionality Reduction**:
   - The mean vector was calculated, and images were centered by subtracting the mean.
   - The covariance matrix was computed, followed by eigenvalue decomposition to get eigenvalues and eigenvectors.
   - The eigenvectors corresponding to the top eigenvalues were selected to form the projection matrix, reducing dimensionality while retaining maximum variance.

3. **Training and Testing**:
   - The dataset was split into training (50%) and testing (50%) sets.
   - Multiple variance percentages were considered (80%, 85%, 90%, 95%) to decide how many principal components to keep.
   - K-Nearest Neighbors (KNN) classifier with varying neighbors (1, 3, 5, 7) was used to classify the reduced features.

4. **Evaluation**:
   - The classifier achieved an accuracy of 94% with 36 principal components (80% variance) and K=1 neighbor.

## Results
- **Best Accuracy**: 94% using 36 principal components (80% variance) with K=1 neighbor.
- **Visualization**: A graph was plotted to show the relationship between the number of principal components and the explained variance.



Link to the data-set: [Here](https://www.kaggle.com/datasets/kasikrit/att-database-of-faces/data)
