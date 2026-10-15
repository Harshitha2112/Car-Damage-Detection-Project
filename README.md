# 🚗 AI-Based Car Damage Detection and Smart Recommendation System

An AI-powered web application that detects car damage from uploaded images, identifies the damaged areas, classifies damage severity, estimates repair costs, and recommends suitable repair shops based on service requirements and pricing.

## 📌 About the Project

Car owners may struggle to identify vehicle damage, understand repair costs, and find a reliable repair shop. Sometimes, customers are charged excessively even for minor damage because they lack information about repair requirements and alternative service prices.

This project aims to make the car repair process more transparent and convenient using Artificial Intelligence and Machine Learning.

Users can upload an image of a damaged car and receive damage analysis, estimated repair costs, and shop recommendations to help them make informed repair decisions.

## ✨ Key Features

### 1. 🔍 AI-Based Car Damage Detection
- Upload a car image for damage analysis.
- Detect visible damage such as scratches, dents, cracks, broken parts, paint peeling, glass damage, missing parts, and tire damage.
- Display detected damage with bounding boxes and labels.

### 2. 🚘 Car Parts Identification
- Identify relevant car components, such as bumpers, doors, windshields, hood, roof, and other vehicle parts.
- Help associate detected damage with the affected vehicle area.

### 3. 📊 Damage Severity Classification
- Classify detected damage into three categories:
  - **Minor**
  - **Moderate**
  - **Severe**
- Use the severity result to help determine appropriate repair recommendations.

### 4. 💰 Car Repair Cost Estimation
- Estimate the expected repair cost based on relevant information, including car model, damage type, severity, and applicable service prices.
- Help customers understand potential repair expenses before contacting a mechanic.
- Support more transparent repair decisions.

*Note: Estimated prices are indicative and may differ from the final quotation provided by a repair shop.*

### 5. 🏪 Smart Repair Shop Recommendation
- Compare service prices offered by registered mechanics or repair shops.
- Identify shops that provide the required repair service.
- Recommend a suitable shop based on service availability and price comparison.
- Help customers find affordable repair options instead of relying on a single quotation.

### 6. 👤 Customer and Mechanic Accounts
- Customer registration and login.
- Mechanic registration and login.
- Mechanic service listings and price ranges.
- Access to relevant repair recommendations.

### 7. 🛠️ Repair Recommendations
- Suggest suitable repair services based on the detected damage and severity.
- Recommend repair products for eligible minor damage cases.
- Guide users toward professional repair services for more serious damage.

## 🔄 How It Works

1. The customer registers or logs in.
2. The customer uploads an image of the damaged car.
3. The AI model detects visible damage.
4. The system identifies relevant car parts and classifies severity where supported.
5. The application determines the appropriate repair requirements.
6. The system estimates the repair cost using available vehicle and service pricing information.
7. The application compares available repair shops and their service prices.
8. The customer receives repair guidance, an estimated cost, and suitable shop recommendations.

## 🧠 Technologies Used

| Technology | Purpose |
|---|---|
| Python | Backend programming and AI integration |
| Flask | Web application backend |
| YOLO | Car damage detection and car parts detection/segmentation |
| Machine Learning | Damage severity classification |
| OpenCV | Image processing |
| Pillow (PIL) | Image handling and drawing detection results |
| HTML5 and CSS3 | Frontend structure and styling |
| JavaScript | Frontend interactions, where applicable |
| SQLite | User, mechanic, service, and application data storage |
| Google Colab | Model training and evaluation |

*The technologies listed should be adjusted to match the libraries and database actually used in the final implementation.*

## 🏗️ System Architecture

```text
                 Customer / Mechanic
                          |
                          v
                    Flask Web App
                          |
              +-----------+-----------+
              |                       |
              v                       v
        Image Upload             User Accounts
              |                       |
              v                       v
      AI Damage Detection       Mechanic Services
              |
              v
       Car Parts Identification
              |
              v
       Damage Severity Analysis
              |
              v
       Repair Recommendation
              |
              v
       Repair Cost Estimation
              |
              v
       Shop Price Comparison
              |
              v
       Recommended Repair Shops
```

## 📂 Project Structure

```text
car-damage-detection/
│
├── app.py
├── best.pt
├── database.db
├── users.db
│
├── static/
│   ├── css/
│   ├── js/
│   └── images/
│
├── templates/
│   ├── index.html
│   ├── login.html
│   ├── register.html
│   ├── upload.html
│   ├── results.html
│   └── recommendations.html
│
├── requirements.txt
└── README.md
```

*This is an illustrative structure. Update the filenames to match your repository. Include other model weights, such as the parts and severity models, if your application loads them.*

## ⚙️ Installation and Setup

### Prerequisites

- Python 3.10 or another version compatible with your installed dependencies.
- pip package manager.
- Git (optional).
- Trained model weights required by the application.

### 1. Clone the Repository

```bash
git clone <your-repository-url>
cd car-damage-detection
```

Alternatively, download the repository as a ZIP file and extract it.

### 2. Create a Virtual Environment

```bash
python -m venv venv
```

Activate it on Windows:

```bash
venv\Scripts\activate
```

### 3. Install Dependencies

If the repository contains a `requirements.txt` file:

```bash
pip install -r requirements.txt
```

Otherwise, install the packages specified by your application's imports and compatible model requirements.

### 4. Configure the Model Files

Place the trained model weights in the paths expected by `app.py`. Ensure the application loads the correct model for each task.

For example:

```text
models/
├── best_car_damage_9class_v1.pt
├── parts_segmentation.pt
└── best_car_severity_v1.pt
```

Update the paths in your Python code if your model files are stored elsewhere.

### 5. Configure Environment Variables

If your application uses email OTP verification or other credentials, configure the required environment variables securely. Do not commit passwords, App Passwords, API keys, or secret keys to GitHub.

### 6. Run the Application

```bash
python app.py
```

Open the local address shown in the Flask terminal, commonly:

```text
http://127.0.0.1:5000/
```

## 📈 Model Evaluation

The project uses trained computer vision models to analyze vehicle images.

Evaluation should include metrics appropriate to each task:

| Task | Evaluation Metrics |
|---|---|
| Damage detection | Precision, Recall, mAP@50, mAP@50–95 |
| Car parts detection/segmentation | Precision, Recall, mAP and segmentation metrics where applicable |
| Severity classification | Accuracy, Precision, Recall, F1-score and confusion matrix |

Model performance depends on the training dataset, image quality, class distribution, and testing conditions.

Actual evaluation results should be reported using the final model weights and a held-out test dataset.

## 🎯 Project Objectives

- Automate the identification of visible car damage.
- Provide useful information about damage type, location, and severity.
- Help customers understand expected repair expenses.
- Compare repair service prices across available shops.
- Recommend suitable and affordable repair options.
- Improve transparency in the vehicle repair process.

## ⚠️ Limitations

- The system analyzes visible damage and may not identify hidden structural or mechanical problems.
- Predictions depend on image quality, lighting, viewing angle, and the training data.
- Repair cost estimates are indicative and depend on vehicle model, parts, labor, location, and shop pricing.
- Shop recommendations depend on the accuracy and availability of registered service and pricing information.
- AI-generated results should not replace a professional vehicle inspection, especially for severe damage or safety-critical components.

## 🔮 Future Enhancements

- Expand the training dataset to improve detection across different car models and damage conditions.
- Improve detection performance on complex and overlapping damage.
- Integrate more verified repair shops and updated service pricing.
- Add repair booking, status tracking, and customer notifications.
- Deploy the application to a cloud platform for wider accessibility.

## 👥 Intended Users

- Car owners looking for preliminary damage assessment.
- Mechanics and repair shops offering vehicle repair services.
- Users comparing service prices before choosing a repair provider.

## 🌟 Expected Impact

The project combines computer vision, machine learning, and price-based recommendations to make preliminary car damage assessment more accessible. By presenting repair estimates and comparing available shop prices, it aims to help customers make informed decisions and reduce the risk of paying unnecessarily high prices for minor damage.

## 👩‍💻 Author

**Harshitha U.**

AI-Based Car Damage Detection and Smart Recommendation System

---

⭐ If you find this project interesting, consider starring the repository!
