# My HTML Site with Dockerized CI/CD Pipeline

This project demonstrates a basic static HTML site hosted via Docker, pushed to Docker Hub, and deployed using a Jenkins CI/CD pipeline.

## 📁 Project Structure

```
my-html-site/
├── index.html
├── Dockerfile
├── README.md
└── Jenkinsfile
```

## 📄 index.html

A simple HTML page:

```html
<!DOCTYPE html>
<html>
<head><title>My Site</title></head>
<body><h1>Hello from Docker CI/CD</h1></body>
</html>
```

## 🐳 Dockerfile

```Dockerfile
FROM nginx:alpine
COPY index.html /usr/share/nginx/html/index.html
```

## 🚀 Steps to Run

### 1. Build & Push to GitHub

```bash
git init
git add .
git commit -m "Initial commit"
git remote add origin https://github.com/your-username/my-html-site.git
git push -u origin master
```

### 2. Build & Push Docker Image

```bash
docker build -t your-dockerhub-username/my-html-site .
docker login
docker push your-dockerhub-username/my-html-site
```

### 3. Jenkins CI/CD Pipeline

```groovy
pipeline {
  agent any
  stages {
    stage('Build & Push Docker Image') {
      steps {
        sh 'docker build -t your-dockerhub-username/my-html-site .'
        sh 'docker login -u your-dockerhub-username -p your-password'
        sh 'docker push your-dockerhub-username/my-html-site'
      }
    }
  }
}
```

---

## 📦 Output

Once deployed, you can view the HTML site from your Docker container via:

```bash
docker run -d -p 8080:80 your-dockerhub-username/my-html-site
```

Open in browser: [http://localhost:8080](http://localhost:8080)
