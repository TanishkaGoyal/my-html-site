pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                script {
                    // Build the Docker image, but don't push it
                    docker.build('my-image')
                }
            }
        }
    }
}
