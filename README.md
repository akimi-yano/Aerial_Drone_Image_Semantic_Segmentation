# Aerial Drone Image Semantic Segmentation

### Project Summary:
This project creates a machine learning model to operate a semantic segmentation on aerial images taken by drones, using PyTorch. The number of segmentation classes is **12**.

---

### Dataset Description:

This dataset consists of `3,269` images in **12 classes** (including background). All images were taken from drones in a variety of scales. Below are sample images from some of the classes present in the dataset:

TODO: UPDATE - ![](./visuals/sports_classification_image.jpg?raw=true)

---

### Machine Learning Model Architecture:

I used pretrained model `deeplabv3_resnet101` with the pretrained weight and and modified the final Conv2D layer of the classifier to match the number of required output classes for the segmentation task of **12**. 

---

### Data Augmentation:

For the training dataset, I applied the following data augmentation to avoid overfitting:

```
transforms.extend([
                A.HorizontalFlip(p=0.5),
                A.VerticalFlip(),
                A.ShiftScaleRotate(scale_limit=0.2, rotate_limit=0, shift_limit=0.2, p=0.5, border_mode=0),])
```

---

### Training Hyperparameters:

* Epochs: `30` with `EarlyStopping` with patience of `10`
  
* Optimizer: `Adam`

* Learning Rate: `0.0001`

* Batch size: `8`

---

### Loss and Accuracy:

TODO: UPDATE - ![](./visuals/sports_classification_loss.png?raw=true) 

TODO: UPDATE - ![](./visuals/sports_classification_accuracy.png?raw=true)

---

### Accuracy on Test Dataset for Kaggle Submission

The configurations discussed above, yielded a score of **0.76993** on the Kaggle's Leaderboard.

TODO: UPDATE - ![](./visuals/sports_classification_kaggle_leaderboard.png?raw=true)
