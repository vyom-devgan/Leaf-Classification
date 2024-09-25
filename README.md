# Leaf Classification: Diseased vs. Fresh

This project focuses on using a **Convolutional Neural Network (CNN)** to classify images of **diseased leaves** and **fresh leaves**. The model was built using **PyTorch** with **ResNet18** as the base architecture, and several techniques were applied to improve model performance and prevent overfitting.

## Dataset and Preprocessing
The dataset contains images split into two categories: **diseased** and **fresh leaves**. It's further divided into training, validation, and test sets.

### Preprocessing Steps:
- **Training set**:
  - Applied data augmentation: random cropping and horizontal flipping.
  - Normalized pixel values using ImageNet's mean and standard deviation.
- **Validation and test sets**:
  - Resized images to 256x256, cropped them to 224x224, and normalized without augmentation.

## Model and Techniques
We used **ResNet18**, a pre-trained model on ImageNet, for its robust feature extraction capabilities. The final fully connected layer was modified to output predictions for 2 classes (fresh vs. diseased).

### Key Techniques:
- **Loss function**: Cross-entropy loss.
- **Optimizer**: Adam with a learning rate of 0.001.
- **Learning rate scheduler**: ReduceLROnPlateau to decrease the learning rate when validation loss plateaued.
- **Early stopping**: Stops training if validation accuracy doesn’t improve for 10 consecutive epochs.

## Training and Evaluation Results
The model trained over **25 epochs**, but early stopping triggered before all epochs were completed. The final model achieved:

- **Accuracy**: 1.00
- **Precision**: 1.00
- **Recall**: 1.00
- **Confusion Matrix**: [[3 0][0 5]]


This result indicates the model correctly classified all the fresh and diseased leaves in the test set.

## Challenges
The biggest challenge was avoiding overfitting since ResNet18 is a powerful model, and the dataset wasn’t large. **Data augmentation** and **early stopping** helped the model generalize better and avoid memorizing the training data.

## Potential Applications
The techniques used here can be applied in many other domains, such as:
- **Medical imaging**: Detecting diseases from X-rays or other medical scans.
- **Agriculture**: Identifying crop diseases or monitoring plant health.
- **Manufacturing**: Automated defect detection in product assembly lines.

---