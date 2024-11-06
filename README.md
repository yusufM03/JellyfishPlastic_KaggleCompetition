# Jellyfish vs. Plastic Classification with Vision Transformer (ViT)

[**Kaggle Competition**](https://www.kaggle.com/competitions/mlo2024mlact/overview) | 
[**Kaggle Profile**](https://www.kaggle.com/yusuf03) |

## Table of Contents
1. [Project Overview](#project-overview)
2. [Dataset Description](#dataset-description)
3. [Installation](#installation)
4. [Code Structure](#code-structure)
5. [Model Training and Evaluation](#model-training-and-evaluation)
6. [Results](#results)
7. [Future Work](#future-work)
8. [Acknowledgments](#acknowledgments)

---

## Project Overview

The goal of this project is to classify images into six distinct classes: five classes representing different species of jellyfish and one class depicting plastic pollution. The project is built to help raise awareness about the threats posed by plastic waste to marine life, especially sea turtles. The model is designed to minimize classification errors with a focus on distinguishing jellyfish from plastic accurately. 

Using Vision Transformer (ViT), a deep learning model well-suited for visual tasks that require attention to fine details, I achieved a classification accuracy score of **0.98750**.

---

## Dataset Description

The dataset provided for this competition contains 1,380 images in two main folders:
- **train/**: Contains six subfolders, one per class (five jellyfish species and one plastic pollution class).
- **test/**: Contains 480 images, used for generating predictions for submission.

### Custom Scoring System
- **Heavy penalty** for classifying plastic as jellyfish.
- **Moderate penalty** for classifying jellyfish as plastic.
- **Minor penalty** for confusion among different jellyfish classes.

---

## Installation

### Requirements
To run the code, you'll need the following dependencies:

```bash
# Basic libraries
pip install -r requirements.txt

```

---

## Code Structure

The project consists of a single Jupyter Notebook and several scripts. Below is the structure of the files and their purposes:

```plaintext
├── ML Olympiad - TurtleVision Challenge.ipynb   # Main notebook for model training, evaluation, and prediction
├── requirements.txt                         # Required libraries and dependencies
└── README.md                                # Project documentation
```

### File Descriptions

- **ML Olympiad - TurtleVision Challenge.ipynb**: Contains the end-to-end code for data loading, model setup, training, evaluation, and submission.

---

## Model Training and Evaluation

### Vision Transformer (ViT)
The ViT model was selected for this project because of its capability to distinguish fine details in images. It was fine-tuned on the dataset to improve accuracy on this six-class classification task. The ViT model splits each image into patches and processes them using a transformer to capture spatial dependencies, which is especially useful for distinguishing jellyfish from plastic.

### Training Process
1. **Data Loading**: The images were loaded and preprocessed, with augmentations like random rotations, cropping to improve robustness.
2. **Model Fine-tuning**: The pre-trained ViT model was fine-tuned on the jellyfish vs. plastic dataset using cross-entropy loss.
3. **Custom Penalties**: After training, custom penalty weights were applied to the predictions based on the competition rules.

### Evaluation
The model was evaluated based on both accuracy and penalties, with particular attention to minimizing misclassifications between jellyfish and plastic.

#### Key Metrics
- **Accuracy**: 0.98750 on the competition test set.
- **Penalties**: Adjusted post-training to adhere to scoring rules.

---

## Results

The ViT model achieved an impressive accuracy score of **0.98750** on the competition leaderboard achieving the third place. This performance is a result of effective feature extraction from ViT’s attention mechanism, which helped the model identify and distinguish subtle visual differences between jellyfish and plastic.

---

## Future Work

To further enhance the model's performance, potential improvements include:
1. **Hyperparameter Tuning**: Experimenting with different learning rates, batch sizes, and attention head settings.
2. **Model Ensemble**: Combining the ViT model with other architectures, such as ResNet or EfficientNet, to capture complementary features.

---

## Acknowledgments

Thank you to Kaggle and the dataset providers for making this competition and dataset available. The project demonstrates the powerful applications of AI in addressing real-world environmental issues and contributes to efforts in marine conservation.

## License
This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
