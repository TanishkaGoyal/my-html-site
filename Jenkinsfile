pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                script {
                    // Build the Docker image
                    docker.build('tanishkagoyal/my-html-site') // Replace with your Docker Hub username/repository
                }
            }
        }
        stage('Push') {
            steps {
                script {
                    // Push the Docker image to Docker Hub
                    sh 'docker push tanishkagoyal/my-html-site' // Replace with your Docker Hub username/repository
                }
            }
        }
    }
}
