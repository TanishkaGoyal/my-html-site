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
