# PS-23: 
🫁 COVID-19 & Lung Disease Detection from Chest X-rays

Deep Learning | Healthcare AI | Explainable AI

A deep learning project that classifies chest X-ray images into four categories using MobileNetV2 and uses Grad-CAM to visualize the regions influencing model predictions.

🎯 Classes

- 🦠 COVID-19
- 🫁 Lung Opacity
- 🧬 Viral Pneumonia
- ✅ Normal

🚀 Tech Stack

"Python" · "TensorFlow/Keras" · "MobileNetV2" · "OpenCV" · "Scikit-learn" · "Matplotlib"

📊 Model Performance

Metric| Score
Test Accuracy| 87%
Macro F1-Score| 0.87
Trainable Parameters| 164,484

🔍 Key Features

- Transfer learning with ImageNet-pretrained MobileNetV2.
- Image preprocessing and data augmentation.
- Four-class classification and confusion matrix analysis.
- Grad-CAM heatmaps to investigate model attention and potential shortcut learning.

📂 Dataset

COVID-19 Radiography Database — 21,165 chest X-ray images.

🔗 "Download Dataset from Kaggle" (https://www.kaggle.com/datasets/tawsifurrahman/covid19-radiography-database)

⚙️ Getting Started

git clone https://github.com/adharsh2006/Deep_learning.git
cd Deep_learning
pip install tensorflow numpy pandas scikit-learn matplotlib seaborn opencv-python-headless

Open "COVID19_Xray_Classification.ipynb" in Google Colab, configure your Kaggle API credentials, and run the notebook cells.

⚠️ Disclaimer

This project is for educational and research purposes only. It is not intended to replace professional medical diagnosis.

👨‍💻 Author

V S Adharsh
B.Tech CSE (AI & ML) | SRM Institute of Science and Technology, Trichy

"GitHub Profile" (https://github.com/adharsh2006)
