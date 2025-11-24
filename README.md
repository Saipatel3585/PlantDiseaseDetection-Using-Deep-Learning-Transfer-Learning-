🌿 Plant Disease Detection using Deep Learning (ResNet50 Transfer Learning)

This repository contains a complete deep-learning pipeline for plant disease classification using Transfer Learning with ResNet50.
The model is trained on the PlantVillage dataset and includes automated dataset downloading, preprocessing, data augmentation, transfer learning, fine-tuning, evaluation, and model export.

This code is optimized for Google Colab and can train quickly using a reduced dataset with a current accuracy of ~78.55%.

📌 Highlights

🔍 Transfer Learning using ResNet50 (ImageNet pretrained)

⚙️ Automated dataset download using KaggleHub

🧼 Data preprocessing + augmentation

⚡ Fast training approach (1 epoch + 1 fine-tune)

🧪 Train/Validation/Test split

💾 Exports model as resnet50_plantvillage.h5

🟩 Fully Colab-compatible

📂 Project Structure
├── plantdiseasedetection.py        # Main training script
├── resnet50_plantvillage.h5        # Trained model (generated after running)
├── plant_village_dataset.csv       # Auto-generated CSV of images
└── README.md                       # Project documentation

📦 Installation

Install necessary Python packages:

pip install tensorflow kagglehub pandas numpy scikit-learn

▶️ Running the Script

Run the Python script:

python plantdiseasedetection.py


This will:

Download the PlantVillage dataset via KaggleHub

Create a CSV containing image paths and labels

Prepare training, validation, and test datasets

Build a ResNet50 transfer learning model

Train the classifier head

Fine-tune deeper layers

Evaluate test accuracy

Save the trained model (.h5)

📊 Current Model Performance

Test Accuracy: 78.55%

Model: ResNet50

Training Mode: Fast (1 epoch + 1 fine-tune epoch)

Dataset: 20% sample for faster training

This accuracy is expected since only a smaller subset of the dataset and fast training mode were used.

🔍 Dataset Information

This project uses the PlantVillage dataset:

Automatically downloaded using:

kagglehub.dataset_download("adilmubashirchaudhry/plant-village-dataset")


The dataset contains:

50,000+ labeled plant leaf images

38+ plant disease classes

🤖 Model Architecture

Base Model:

ResNet50

Pretrained on ImageNet

Convolutional layers frozen initially

Custom Top Layers:

Global Average Pooling

Dense(256) + ReLU

Dropout(0.4)

Dense(num_classes) + Softmax

Training Procedure:

Train classifier head

Fine-tune deeper layers

Evaluate

📈 Improving Accuracy

To increase accuracy from 78.55% → 90–96%, consider:

✔ Increase training data

Use 4000–6000 images instead of 20% sample.

✔ Increase image size

Change from 128×128 → 224×224.

✔ Train longer

Use 5–10 epochs + fine-tuning.

✔ Use MobileNetV2

Much faster and often higher accuracy on smaller datasets.

If you want, I can create a MobileNetV2 version or high-accuracy version of the script.

🔮 Future Enhancements

Convert model to TFLite for mobile app deployment

Add Grad-CAM heatmaps for model explainability

Deploy using Flask API or Streamlit UI

Replace ResNet50 with EfficientNet or MobileNetV3

🤝 Contributing

Contributions, pull requests, and suggestions are welcome!

📬 Contact

If you need help extending or deploying this project, feel free to reach out ✨
