# DevOps Lab – All 7 Experiments

---

# Experiment 1 – Git Operations + Pull Request

## Aim
To perform Git commands, create branch, push code, and merge using Pull Request.

## Where to Do It
Use Git Bash / Command Prompt / Terminal

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

### Step 3: Create Branch

```bash
git checkout -b feature/hello
```

### Step 4: Add New File

```bash
echo "Hello from feature branch" > hello.txt
git add hello.txt
git commit -m "Added hello.txt"
```

### Step 5: Connect GitHub Repo

```bash
git remote add origin <repo-url>
git push -u origin feature/hello
```

### Step 6: On GitHub Website

Create Pull Request → Merge Pull Request

### Step 7: Update Main Branch

```bash
git checkout main
git pull origin main
```

## Expected Output

Repository created and merged successfully.
