# ✅ Experiment 1 – Git Operations + Pull Request

## Aim
To perform Git commands, create branch, push code, and merge using Pull Request.

## Where to Do It
Use **Git Bash / Command Prompt / Terminal**

## Steps

### Step 1: Create Project Folder

```bash
mkdir myproject
cd myproject
git init
```

### Step 2: Create README File

```bash
echo "My DevOps Project" > README.md
git add README.md
git commit -m "Initial commit"
```

### Step 3: Create New Branch

```bash
git checkout -b feature/hello
```

### Step 4: Add New File

```bash
echo "Hello from feature branch" > hello.txt
git add hello.txt
git commit -m "Added hello.txt"
```

### Step 5: Connect to GitHub

```bash
git remote add origin <repo-url>
git push -u origin feature/hello
```

### Step 6: GitHub Website

Create Pull Request → Merge Pull Request

### Step 7: Update Main Branch

```bash
git checkout main
git pull origin main
```
# ✅ Experiment 2 – Dockerize Flask App + Push Docker Hub

## Aim
To containerize Flask application using Docker.

## Where to Do It
Use **VS Code + Terminal + Docker Desktop**

## Step 1: Create app.py

```python
from flask import Flask
app = Flask(__name__)

@app.route('/')
def home():
    return "Hello from Dockerized Flask!"

app.run(host='0.0.0.0', port=5000)
```

## Step 2: Create requirements.txt

```txt
flask
```

## Step 3: Create Dockerfile

```dockerfile
FROM python:3.11-slim
WORKDIR /app
COPY requirements.txt .
RUN pip install -r requirements.txt
COPY . .
EXPOSE 5000
CMD ["python","app.py"]
```

## Step 4: Build Image

```bash
docker build -t username/flask-app .
```

## Step 5: Run Container

```bash
docker run -p 5000:5000 username/flask-app
```

## Step 6: Push Docker Hub

```bash
docker login
docker push username/flask-app
```

## Expected Output

Open browser:

http://localhost:5000

Shows:

Hello from Dockerized Flask!

## Expected Output

Repository created and merged successfully.


# ✅ Experiment 3 – Monolithic Application using Flask

## Aim
To develop monolithic application using Flask.

## Where to Do It
Use **VS Code + Terminal**

## app.py

```python
from flask import Flask, request

app = Flask(__name__)
students = []

@app.route('/')
def home():
    return "Monolithic App"

@app.route('/students', methods=['GET'])
def view():
    return str(students)

@app.route('/students', methods=['POST'])
def add():
    students.append(request.json)
    return "Student Added"

app.run(debug=True)
```

## Run Commands

```bash
pip install flask
python app.py
```

## Expected Output

Open browser:

http://localhost:5000

Shows:

Monolithic App

# ✅ Experiment 4 – CI Pipeline using GitHub Actions

## Aim
To automatically build Docker image using GitHub Actions.

## Where to Do It
Use **GitHub Repository**

## Create File

.github/workflows/docker-publish.yml

## YAML Code

```yaml
name: CI Pipeline

on:
  push:
    branches: [main]

jobs:
  build:
    runs-on: ubuntu-latest

    steps:
      - uses: actions/checkout@v3
      - run: docker build -t myapp .
```

## Push File

```bash
git add .
git commit -m "CI Added"
git push
```

## Expected Output

Green tick in GitHub Actions.

# ✅ Experiment 5 – Jenkins Pipeline

## Aim
To automate build/test/deploy using Jenkins.

## Where to Do It
Use **Docker + Browser**

## Step 1: Run Jenkins

```bash
docker run -d -p 8080:8080 -p 50000:50000 --name jenkins jenkins/jenkins:lts
```

## Step 2: Get Password

```bash
docker exec jenkins cat /var/jenkins_home/secrets/initialAdminPassword
```

## Step 3: Open Browser

http://localhost:8080

## Step 4: Pipeline Script

```groovy
pipeline {
 agent any
 stages {
   stage('Build'){ steps{ echo 'Build' } }
   stage('Test'){ steps{ echo 'Test' } }
   stage('Deploy'){ steps{ echo 'Deploy' } }
 }
}
```

## Expected Output

Finished: SUCCESS

# ✅ Experiment 6 – Kubernetes Commands

## Aim
To create, scale, expose deployment.

## Where to Do It
Use **Terminal with Kubernetes / Minikube**

## Commands

```bash
kubectl create deployment myapp --image=nginx
kubectl get deployments
kubectl get pods
kubectl scale deployment myapp --replicas=3
kubectl expose deployment myapp --port=80 --type=NodePort
kubectl get services
kubectl delete service myapp
kubectl delete deployment myapp
```

## Expected Output

Deployment and pods created successfully.

# ✅ Experiment 7 – GitHub Actions with Docker Buildx

## Aim
To build and push Docker image using Buildx.

## Where to Do It
Use **GitHub Repository**

## Create File

.github/workflows/buildx.yml

## YAML Code

```yaml
name: Buildx Pipeline

on:
  push:
    branches: [main]

jobs:
  docker:
    runs-on: ubuntu-latest

    steps:
      - uses: actions/checkout@v3
      - uses: docker/setup-buildx-action@v3
```

## Push File

```bash
git add .
git commit -m "Buildx Added"
git push
```

## Expected Output

Docker image pushed automatically.
