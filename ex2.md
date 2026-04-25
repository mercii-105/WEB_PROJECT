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
