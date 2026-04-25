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
