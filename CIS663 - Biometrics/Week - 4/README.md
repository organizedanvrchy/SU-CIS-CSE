# Face Recognition
This document provides an overview of face recognition in biometrics, focusing on its challenges, steps, and key algorithms like Viola-Jones.

## Algorithmic Bias

### Issues with Face Recognition
- **Face Detection**: 
    - Detecting faces in an image is a complex task that can be influenced by factors such as lighting, occlusion, angle, and the presence of non-human faces or artifacts.
    - Face detection is prone to errors like false positives (detecting non-faces as faces) and false negatives (failing to detect actual faces).

- **Face Recognition**:
    - This step involves matching a detected face to a pre-registered face in a database. 
    - Recognition performance can be affected by poor image quality, changes in appearance, aging, or variations in facial expressions.
    - Algorithmic bias can lead to misidentification, especially for individuals of certain ethnicities, genders, or age groups, leading to unequal error rates across different demographic groups.


## Face Detection Steps
Face detection is the initial step in a face recognition pipeline. The goal is to identify regions in an image that likely contain a face. The process typically involves the following stages:

1. **Face Detection**:
    - The first stage involves identifying regions in an image where faces are likely to appear.
    - It can be performed using various algorithms, such as Haar Cascades, deep learning-based methods, or template matching.

2. **Projection**:
    - Once faces are detected, the next step is to project or map these regions to a computational space where further analysis can occur.
    - In many systems, this involves converting the face into a feature vector, a mathematical representation that encodes information about facial characteristics.

3. **Database Search**:
    - The final stage of detection involves searching through a database of known faces to find the closest match.
    - This step typically uses methods like nearest neighbor search, often employing algorithms such as k-Nearest Neighbors (k-NN) or support vector machines (SVM).


## Viola-Jones Algorithm
The Viola-Jones algorithm is a foundational face detection method that was developed in 2001. It uses machine learning and a series of techniques to perform efficient face detection. The algorithm incorporates the following key components:

### Haar Features
Haar-like features are used to describe the appearance of objects in an image. These features are based on the differences in intensity between adjacent rectangular regions in an image. Viola-Jones specifically uses these to detect faces by identifying specific patterns.
- **Horizontal Two Rectangle Feature**: 
    - This feature is used to detect edges or transitions in lighting (light/dark) in the horizontal direction. 
    - It compares the sum of pixel intensities in two adjacent rectangular regions, one light and one dark. If the difference in sums exceeds a threshold, the region is likely to be a face.

### Integral Image
The integral image is a computational technique that allows the fast calculation of rectangular features. 
- The integral image at any point (x, y) contains the sum of all pixel values in the region from (0, 0) to (x, y).
- This allows for the quick computation of sums for any rectangular region in the image, enabling efficient feature extraction.

#### Formula for Integral Image:
For an image I, the integral image at a point (x, y) is defined as:
`II(x, y) = I(x, y) + II(x-1, y) + II(x, y-1) - II(x-1, y-1)`

Where `II(x, y)` is the sum of pixel values from the top-left corner to (x, y).

### Adaboost
Adaboost (Adaptive Boosting) is a machine learning algorithm used to combine multiple weak classifiers to create a strong classifier. 
- **Ensemble Predictor**: Adaboost uses a collection of weak classifiers, combining them into a stronger, more accurate predictor.
- **Weak Learners**: These are simple classifiers that individually perform slightly better than random guessing.
- **Adaboost Algorithm**:
    - **Step 1**: Assign equal weights to all training samples.
    - **Step 2**: Train a weak classifier on the weighted samples, and calculate the error (misclassifications).
    - **Step 3**: Increase the weights of misclassified samples to emphasize their importance in the next iteration.
    - **Step 4**: Combine the weak classifiers into a strong one by assigning a weight to each classifier based on its accuracy.

#### The Adaboost formula:
The final output of Adaboost is a weighted sum of the individual weak classifiers:
`f(x) = Σα_t * h_t(x)`

Where:
- `f(x)` is the final classifier.
- `α_t` is the weight of the t-th weak classifier `h_t(x)`.

- **Best Classifiers**: In the context of the Viola-Jones algorithm, the best classifiers are the ones with the lowest error rate, and they are given higher weights in the final model.

### Cascading
Cascading is a technique used to optimize the speed and efficiency of the face detection process. The main idea is to apply a series of classifiers in stages, where each stage filters out regions that are unlikely to contain faces. This reduces the computational load by focusing on promising areas of the image.

- **Cascading Classifiers**: A sequence of classifiers that progressively narrow down the regions that need to be analyzed in detail.
    - The first classifiers in the cascade are simple and fast but may produce false positives.
    - As the process continues, the classifiers become more complex and precise.
  
- **Detection Cascade**: 
    - The detection cascade consists of multiple stages, each designed to reject non-face regions quickly and focus computational resources on likely face regions.
    - Each classifier in the cascade is trained to detect faces at different scales, and at each stage, only regions that pass the classifier’s test are forwarded to the next stage.
    - This hierarchical process ensures that the majority of non-face regions are filtered out quickly, leading to improved detection efficiency.

---
