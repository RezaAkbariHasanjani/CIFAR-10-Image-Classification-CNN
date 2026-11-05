# CIFAR-10 Image Classification Using CNN

Image classification on the CIFAR-10 dataset using a Convolutional Neural Network (CNN) built with TensorFlow and Keras.


## Project Overview

This project implements a Convolutional Neural Network (CNN) using TensorFlow and Keras to classify images from the CIFAR-10 dataset into 10 different categories.

The main goal is to build, train, and evaluate a deep learning model for image classification.

## Dataset

The project uses the **CIFAR-10** dataset.

- Total images: 60,000
- Image dimensions: 32 × 32 pixels
- Number of color channels: 3 (RGB)
- Number of classes: 10

### Classes

1. Airplane
2. Automobile
3. Bird
4. Cat
5. Deer
6. Dog
7. Frog
8. Horse
9. Ship
10. Truck

The original training and testing datasets are combined and saved in a compressed NumPy file. The complete dataset is then split into training and testing sets.

## Technologies and Libraries

- Python
- TensorFlow
- Keras
- NumPy
- Scikit-learn
- Matplotlib
- Seaborn
- Jupyter Notebook

## Data Preprocessing

The following preprocessing steps are performed:

- Loading the CIFAR-10 dataset.
- Combining the original training and testing datasets.
- Saving the complete dataset using `np.savez_compressed()`.
- Splitting the data into training and testing sets using `train_test_split()`.
- Using stratified sampling to preserve class distribution.
- Normalizing pixel values to the range [0, 1] using the Keras `Rescaling` layer.

The dataset is split as follows:

- Training set: 80% (48,000 images)
- Testing set: 20% (12,000 images)

## CNN Architecture

The model is built using Keras Sequential API.

| Layer | Configuration |
|---|---|
| Input | 32 × 32 × 3 |
| Rescaling | 1/255 |
| Conv2D | 32 filters, 3 × 3, ReLU |
| MaxPooling2D | 2 × 2 |
| Conv2D | 64 filters, 3 × 3, ReLU |
| MaxPooling2D | 2 × 2 |
| Flatten | - |
| Dense | 128 neurons, ReLU |
| Dropout | 0.4 |
| Output | 10 neurons, Softmax |

## Model Compilation

The model is compiled using:

- Optimizer: Adam
- Loss Function: Sparse Categorical Crossentropy
- Evaluation Metric: Accuracy

Sparse categorical crossentropy is used because the class labels are stored as integer values rather than one-hot encoded vectors.

## Model Training

The model is trained with the following configuration:

- Batch size: 100
- Maximum epochs: 20
- Validation split: 10%
- Early Stopping: Enabled
- Early Stopping patience: 3
- Restore best weights: True

Early Stopping monitors validation loss to help prevent overfitting.

## Model Evaluation

The trained model is evaluated using the test dataset.

The following evaluation metrics are used:

- Test Accuracy
- Test Loss
- Precision
- Recall
- F1-score
- Confusion Matrix

## Visualization

The project includes the following visualizations:

1. **Training and Validation Accuracy:** Shows the accuracy changes during training.
2. **Training and Validation Loss:** Helps identify overfitting.
3. **Confusion Matrix:** Visualizes correct and incorrect predictions for all 10 classes.

## Results

The model achieved approximately **72% test accuracy** on 12,000 test images.

The classification report showed different performance levels across the 10 classes.

- Best F1-score: Automobile (0.84)
- Best Recall: Ship (0.88)
- Lowest F1-score: Cat (0.54)

The confusion matrix indicates that Cat and Dog are among the most challenging classes for the model to distinguish.

## How to Run

1. Clone or download this repository.
2. Install the required libraries:

```bash
pip install tensorflow numpy scikit-learn matplotlib seaborn jupyter
```

3. Open the notebook:

```bash
jupyter notebook cifar10.ipynb
```

4. Run the notebook cells sequentially.

## Future Improvements

Possible improvements include:

- Applying Data Augmentation.
- Adding Batch Normalization.
- Experimenting with deeper CNN architectures.
- Tuning hyperparameters.
- Using learning rate scheduling.
- Improving classification performance on visually similar classes.

## Author

Dr.Reza Akbari-Hasanjani
