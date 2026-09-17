# AI Health — Diabetes Risk Prediction System 🏥

An AI-powered web application that predicts diabetes risk from user-provided health parameters using a machine learning model. The application provides real-time predictions through a Flask web application and stores prediction records using Firebase Firestore.

## 🌐 Live Demo

**Live Application:**
https://ai-health-0gry.onrender.com

> **Note:** The live deployment may require Firebase configuration to be available on the deployment environment.

---

## ✨ Features

* **Diabetes Risk Prediction** — Predicts diabetes risk from health-related input parameters.
* **Real-Time Prediction** — Returns a prediction and calculated risk percentage.
* **Health Parameter Analysis** — Uses parameters including:

  * Pregnancies
  * Glucose Level
  * Blood Pressure
  * Skin Thickness
  * Insulin Level
  * BMI
  * Diabetes Pedigree Function
  * Age
* **Machine Learning Model** — Uses a Random Forest Classifier with feature scaling.
* **Prediction Storage** — Stores prediction results in Firebase Firestore.
* **Prediction History API** — Provides an endpoint for retrieving stored prediction records.
* **Web Interface** — Flask serves the application interface through HTML, CSS, and JavaScript.
* **Cloud Deployment** — Deployed using Render.

---

## 🏗️ System Architecture

```text
User
  │
  ▼
Web Interface
(HTML / CSS / JavaScript)
  │
  ▼
Flask Application
  │
  ├── Input Validation
  │
  ├── Feature Scaling
  │
  ├── Random Forest Model
  │
  └── Prediction Processing
          │
          ├──────────────► Prediction Result
          │
          └──────────────► Firebase Firestore
```

---

## 🧰 Technology Stack

### Frontend

* HTML5
* CSS3
* JavaScript

### Backend

* Python
* Flask
* Flask-CORS

### Machine Learning

* Scikit-learn
* Random Forest Classifier
* StandardScaler
* NumPy
* Pandas

### Database

* Firebase Firestore

### Deployment

* Render
* Gunicorn

---

## 🤖 Machine Learning

The application uses a **Random Forest Classifier** to generate diabetes-risk predictions.

The input features are standardized using `StandardScaler` before being passed to the model.

The current implementation uses the following parameters:

```text
Pregnancies
Glucose
Blood Pressure
Skin Thickness
Insulin
BMI
Diabetes Pedigree Function
Age
```

The model returns:

* Prediction result
* Estimated risk percentage

The model configuration includes multiple decision trees with parameters such as `n_estimators`, `max_depth`, `min_samples_split`, `min_samples_leaf`, and balanced class weights.

---

## 🔌 API Endpoints

### `GET /`

Loads the main web application.

### `POST /predict`

Accepts health parameters and returns a diabetes prediction.

Example request:

```json
{
  "pregnancies": 2,
  "glucose": 120,
  "bloodPressure": 70,
  "skinthickness": 20,
  "insulin": 79,
  "bmi": 25.0,
  "diabetesPedigreeFunction": 0.5,
  "age": 30
}
```

Example response:

```json
{
  "prediction": 0,
  "risk_percentage": 18.42
}
```

### `GET /user_predictions/<user_id>`

Retrieves prediction records associated with a user.

---

## 🚀 Getting Started

### 1. Clone the repository

```bash
git clone https://github.com/NareshS24/AI-HEALTH.git
cd AI-HEALTH
```

### 2. Create a virtual environment

```bash
python -m venv venv
```

Activate it on Windows:

```bash
venv\Scripts\activate
```

Activate it on macOS/Linux:

```bash
source venv/bin/activate
```

### 3. Install dependencies

```bash
pip install -r requirements.txt
```

### 4. Configure Firebase

The application uses Firebase Admin SDK and Firestore for storing prediction data.

Create/configure your Firebase service account credentials locally.

**Do not commit your Firebase service-account JSON file to GitHub.**

The repository's `.gitignore` excludes:

```text
serviceAccountKey.json
.env
.env.*
```

### 5. Run the application

```bash
python app.py
```

The application will be available at:

```text
http://localhost:5000
```

---

## 📁 Project Structure

```text
AI-HEALTH/
│
├── static/                     # Frontend static files
├── templates/                  # HTML templates
│
├── app.py                      # Flask application and API endpoints
├── firebase_config.py          # Firebase / Firestore integration
│
├── model_building.py           # Model training
├── feature_engineering.py      # Feature processing
├── eda_analysis.py             # Exploratory data analysis
├── load_model.py               # Model loading utilities
├── save_model.py               # Model saving utilities
├── request_prediction.py       # Prediction request utilities
│
├── diabetes_model.pkl          # Trained model artifact
├── model.pkl                   # Model artifact
├── scaler.pkl                  # Feature scaler
│
├── requirements.txt             # Python dependencies
├── render.yaml                  # Render deployment configuration
├── .gitignore                   # Ignored files and credentials
├── LICENSE                      # MIT License
└── README.md                    # Project documentation
```

---

## 🧪 Development & Testing

The application was developed and manually tested by running the Flask application and checking the prediction flow, API responses, Firebase integration, and user-facing functionality.

The `/predict` endpoint also handles invalid or missing request data and returns an appropriate error response.

---

## 🔐 Security

Firebase service-account credentials are sensitive and must not be committed to the repository.

For local development, keep credentials outside version control and ensure they are excluded through `.gitignore`.

For deployment, configure sensitive credentials through the deployment platform's secure environment/configuration mechanisms rather than storing private credentials in the source repository.

---

## 🤝 Contributing

Contributions are welcome.

1. Fork the repository.
2. Create a feature branch.
3. Make your changes.
4. Test the application.
5. Commit your changes.
6. Open a Pull Request.

For significant changes, please open an issue first to discuss the proposed change.

---

## ⚠️ Medical Disclaimer

This application is intended for **educational and demonstration purposes only**.

The predictions generated by this system should **not be considered medical advice, diagnosis, or treatment recommendations**.

Users should consult qualified healthcare professionals for medical decisions.

---

## 📄 License

This project is licensed under the **MIT License**.

See the [`LICENSE`](LICENSE) file for the complete license terms.

---

## 👨‍💻 Author

**Naresh S**

GitHub:
https://github.com/NareshS24

Portfolio:
https://iamnaresh.me

---

⭐ If you find this project useful, consider giving the repository a star.
