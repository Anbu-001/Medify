# Medify
## 🛠 **1. Build and Run the Flask Application Locally**
```bash
# Clone the repository
git clone https://github.com/Anbu-001/Medify.git

# Install dependencies
pip install -r requirements.txt

# Run the Flask app locally
python app.py
```
## 🐳 2. Containerizing the Application with Docker

```bash
# Build the Docker image
docker build -t flask-app .
```

```bash
# Run the container locally
docker run -p 5000:5000 flask-app
```

Test the app at [http://localhost:5000](http://localhost:5000).

---

## 🚢 3. Deploying on Minikube

### Step 1: Start Minikube
```bash
minikube start
```

### Step 2: Build the Docker Image Inside Minikube
```bash
eval $(minikube docker-env)
docker build -t flask-app .
```

### Step 3: Deploy Flask App to Kubernetes
```bash
kubectl apply -f deployment.yaml
```

### Step 4: Check Pod and Service Status
```bash
kubectl get pods
kubectl get svc
```

### Step 5: Access the Flask App
```bash
minikube service flask-service --url
```

If using **NodePort**, find the Minikube IP:
```bash
minikube ip
```

Then access it via:
```plaintext
http://<minikube-ip>:<NodePort>
```

---

## 📂 Deployment Files
- **Dockerfile** → Instructions to build Flask container.
- **deployment.yaml** → Kubernetes Deployment and Service configuration.
