# Breast-cancer-classification-with-XAI
ResNet50-based BCI Image Classification with Score-CAM Visualization
This project showcases the use of a modified ResNet50 convolutional neural network for classifying brain-computer interface (BCI) image data. The model is augmented with Score-CAM to provide visual explanations of class-specific attention, helping to interpret how the model makes decisions. The notebook is designed to run in a GPU-enabled Kaggle environment and focuses on patch-level classification of BCI signals from images sized 40x40, expanded with contextual patches.

The approach begins with importing and preparing the dataset, followed by the fine-tuning of a pre-trained ResNet50 backbone. All layers are initially frozen to preserve the general features learned during ImageNet pretraining. Selective layers—layer3, layer4, and the fc layer—are then unfrozen to fine-tune the model on domain-specific features relevant to BCI data.

To further enhance interpretability, this notebook integrates the Score-CAM technique using the pytorch-grad-cam library. After training, Score-CAM is applied to visualize the discriminative regions of the image that most influenced the model’s prediction. These visual explanations are superimposed on the original images to help interpret how the model is learning.

The dataset is organized into class-specific directories and processed using standard PyTorch data loaders with normalization and augmentation. Model performance is evaluated using accuracy, precision, recall, F1-score, and confusion matrices.

Training concludes with Score-CAM visualizations that provide intuitive insight into model focus areas, enabling a bridge between model predictions and human-interpretable evidence.

This notebook serves both as a strong classification baseline and an interpretability toolkit for BCI-related image classification tasks.

Get the dataset: https://zenodo.org/records/15179608

📈 Outputs;

🔹 Confusion Matrix

![confusion_40x_patch](https://github.com/user-attachments/assets/555dd796-1c06-4dad-af77-a1f45e980e44)


🔹 ROC Curve (Macro AUC)
![40x-auc-patch](https://github.com/user-attachments/assets/4e1dd57f-7b43-4f50-b4d6-215dd9c9596c)


🔹 Train and Validation Accuracy

![40x-patch](https://github.com/user-attachments/assets/04217f0f-87b7-43b6-a514-d9153b1b8702)


🔹 Score-CAM visualization 

![xai-patch](https://github.com/user-attachments/assets/9c252ae9-0f9f-4d06-ac72-7c1f940efc0d)

