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
