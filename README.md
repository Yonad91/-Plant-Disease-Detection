Plant Disease Detection using VGG16 (TensorFlow + Gradio)

This project implements a Plant Disease Classification System using VGG16 Transfer Learning, trained on the New Plant Diseases Dataset from Kaggle. The notebook automates dataset download, preprocessing, model training, evaluation, and deployment with a Gradio web interface.

🚀 Features

✔ Fully automated Kaggle dataset download using kaggle.json

✔ TensorFlow pipeline with tf.data image pipelines

✔ Transfer Learning using VGG16 (pretrained on ImageNet)

✔ Custom classification head for multi-class plant disease detection

✔ Training logs, checkpoints, LR scheduling, and CSV logging

✔ Accuracy/Loss visualization

✔ Classification report + confusion matrix

✔ Exported .h5 model

✔ Live interactive Gradio web app for image prediction

📁 Dataset

The notebook downloads the New Plant Diseases Dataset automatically from Kaggle:

vipoooool/new-plant-diseases-dataset


The dataset contains images of healthy and diseased plant leaves, organized into:

Project Workflow
1. Install Dependencies

Installs TensorFlow, Gradio, and Kaggle API.

2. Upload kaggle.json & Download Dataset

User uploads Kaggle API token.
The script downloads and extracts the dataset automatically.

3. Create tf.data Pipelines

Efficient, prefetch-optimized image pipelines:

Rescale pixels

Batch + shuffle

Auto-detect class names

4. Build Model (VGG16 + Custom Head)

Load VGG16 (without top layers & frozen weights)

Add:

GlobalAveragePooling

Dense(256, ReLU)

Dropout

Output Softmax layer

5. Train Model

10 epochs

1000 steps per epoch

Callbacks:

Best model checkpoint

ReduceLROnPlateau

CSV Logger

6. Visualize Performance

Plots:

Training & validation accuracy

Training & validation loss

7. Evaluate Model

Generates:

Classification Report

Confusion Matrix

Test accuracy

8. Export & Deploy Model

Saves the final model:
Creates a Gradio interface with:

Prediction

Confidence

Notes

Launches directly inside Colab.

Gradio Demo

After training, a live web app is generated:

Upload an image of a plant leaf

The model predicts:

Disease name

Confidence score

Description message

📦 Requirements

Python ≥ 3.8

TensorFlow ≥ 2.12

Gradio

Kaggle API

NumPy, Matplotlib, Sklearn

🧪 Model Architecture Summary
VGG16 (pretrained, frozen)
    ↓
GlobalAveragePooling2D
    ↓
Dense(256, ReLU)
    ↓
Dropout(0.5)
    ↓
Dense(NUM_CLASSES, Softmax)
Outputs Generated

best_model_plant.h5 – best checkpoint

plant_disease_vgg16_final.h5 – final trained model

training_log_plant.csv – training metrics

Accuracy/Loss graphs

Classification report

Confusion matrix


Group Members

Yonas Ademu----------DBUE/079/13

Tsegaw Shewaye------—DBUE/0786/13

Edilam Girma---------DBUE/0731/13

Dejene Kifle---------DBUE/0727/13

Tsiye H/mariam-------DBUE/0790/13
