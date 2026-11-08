# rock-paper-scissors-recognition-
Hand gesture recognition using image processing, feature extraction and Bayesian classification.
Rock Paper Scissors – Hand Gesture Recognition

Project Overview

This project focuses on developing a hand gesture recognition system capable of classifying three different hand gestures: Rock, Paper, and Scissors.

The system combines image processing techniques, feature extraction, statistical modeling, and classification algorithms to recognize hand gestures based on their visual characteristics.

The main objective is to develop a classification pipeline that transforms raw images into numerical feature representations and uses statistical decision rules to identify the corresponding gesture.

Methodology

1. Image Preprocessing

The first stage involves processing input images to isolate the hand from the background.

The following operations are performed:

* Conversion from RGB to HSV color space.
* Color-based segmentation using HSV thresholds.
* Creation of a binary mask separating the hand from the background.
* Extraction of the hand region for further analysis.

HSV color representation is used because it allows segmentation based on hue, saturation, and brightness components.

2. Feature Extraction

After image segmentation, numerical features are extracted from each binary hand image.

Three features are investigated:

* Feature 1: Ratio of black and white pixels in the left half of the image.
* Feature 2: Ratio between image width and height.
* Feature 3: Number of white pixels along a selected vertical image column.

These features provide a compact numerical representation of hand geometry and are used as input to the classification algorithms.

Feature distributions are visualized to investigate class separability and identify the most informative feature combinations.

3. Dataset Preparation

The dataset contains images belonging to three gesture classes:

* Rock
* Paper
* Scissors

Extracted feature vectors are combined into a single dataset.

The data is divided into training and testing subsets using train_test_split():

* 70% training data
* 30% testing data

Stratified sampling is applied to preserve the class distribution across both subsets.

4. Bayesian Classification

A Bayesian multi-class classifier is implemented to distinguish between the three hand gestures.

The classification approach assumes that feature vectors within each class follow a multivariate Gaussian distribution.

For each class, the following statistical parameters are estimated using training data:

* Mean vector
* Covariance matrix
* Prior class probability

The final classification decision is based on the Maximum A Posteriori (MAP) criterion.

5. Model Evaluation

Classification performance is evaluated using a confusion matrix.

The model achieves an overall classification accuracy of 84.69% on the test dataset.

The confusion matrix is used to analyze the relationship between actual and predicted gesture classes.

6. Feature Separability and Histogram Analysis

Different feature combinations are visualized to investigate how effectively the three gesture classes can be separated.

Rock and Scissors are selected for further binary classification because they exhibit good separability in the selected feature space.

Two-dimensional histograms are used to analyze the distributions of the selected features.

7. Linear Parametric Classification

A linear parametric classifier is developed for distinguishing between Rock and Scissors.

The classifier uses the resubstitution method to estimate an optimal decision boundary.

The implementation involves:

* Estimation of class mean vectors.
* Estimation of covariance matrices.
* Construction of a weighted covariance matrix.
* Optimization of the projection vector.
* Selection of the optimal decision threshold.
* Visualization of the resulting linear classification boundary.

The final decision boundary is plotted together with the training samples.

Technologies & Libraries

* Python
* NumPy
* Matplotlib
* Scikit-image
* Scikit-learn
* Seaborn
* Jupyter Notebook

Repository Structure

rock-paper-scissors-recognition/
│
├── README.md
├── notebooks/
│   └── hand_gesture_recognition.ipynb
│
├── results/
│   ├── feature_visualization.png
│   ├── confusion_matrix.png
│   └── classification_boundary.png
│
├── requirements.txt
└── .gitignore

How to Run

1. Clone the repository:

git clone https://github.com/cicvaricjelena2/rock-paper-scissors-recognition.git

2. Navigate to the project directory:

cd rock-paper-scissors-recognition

3. Install the required dependencies:

pip install numpy matplotlib scikit-image scikit-learn seaborn jupyter

4. Download or provide the Rock Paper Scissors image dataset and organize it into three folders:

Rock Paper Scissors/
├── rock/
├── paper/
└── scissors/

5. Launch Jupyter Notebook:

jupyter notebook

6. Open the notebook and execute the cells.

Key Takeaways

This project demonstrates the application of statistical pattern recognition techniques to a computer vision problem.

It combines image segmentation, feature engineering, probabilistic classification, and linear decision boundary optimization.

The project highlights the importance of selecting informative features and understanding their statistical distributions when designing classification systems.

Author

Jelena Cicvarić

Electrical Engineering | Machine Learning | Data Science

GitHub Profile
