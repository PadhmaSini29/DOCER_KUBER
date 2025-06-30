# 🧠 DockaCure – Container-Driven Breast Cancer Diagnosis

A machine learning–based web application for predicting breast cancer malignancy using an SVM classifier, containerized with Docker and deployed via Kubernetes.

## 🗂️ Project Structure

```
DOCER_KUBER/
├── app.py                # Flask web app
├── svm.py                # SVM training, testing, and prediction logic
├── svm_func.py           # (Alias/module aliasing svm.py functionality)
├── Breast Cancer Data.csv # Input dataset
├── Dockerfile            # Docker setup
├── requirements.txt      # Python dependencies
├── deployment.yaml       # Kubernetes Deployment configuration
├── service.yaml          # Kubernetes Service configuration
```

## 🚀 Features

- Flask-based web interface to input features
- Predicts if a tumor is **Benign** or **Malignant**
- Uses Support Vector Machine (SVM) for classification
- Trained on UCI Breast Cancer dataset
- Dockerized for portable deployment
- Kubernetes manifests included for cloud-native deployment

## 📦 Requirements

- Python 3.7+
- Docker
- Kubernetes (e.g., Minikube or cloud cluster)
- Flask, scikit-learn, pandas, numpy

Install dependencies locally:

```bash
pip install -r requirements.txt
```

## 🧪 Running the App

### 🐳 Docker

Build the image:

```bash
docker build -t docer_kuber_app .
```

Run the container:

```bash
docker run -p 7070:7070 docer_kuber_app
```

Open your browser at: [http://localhost:7070](http://localhost:7070)

### ☸️ Kubernetes

Deploy to Kubernetes:

```bash
kubectl apply -f deployment.yaml
kubectl apply -f service.yaml
```

Then forward the port:

```bash
kubectl port-forward service/docer-kuber-service 7070:7070
```

Access the app at [http://localhost:7070](http://localhost:7070)

## 💡 Usage

1. Navigate to the homepage.
2. Enter 30 numerical features (mean, standard error, and worst of radius, texture, etc.).
3. Submit the form.
4. View prediction result (Benign or Malignant) with SVM confidence and time taken.

## 🧠 Model

- Algorithm: **Support Vector Machine (SVC)**
- Dataset: UCI Breast Cancer Wisconsin
- Accuracy: ~97% (varies with split)

## 📊 Sample Code Highlights

- `svm_func.py`: Handles training, testing, and real-time prediction.
- `app.py`: Flask routes render `home.html` and `result.html`, using `predict_svm()`.

## 📄 License

This project is licensed under the MIT License.
