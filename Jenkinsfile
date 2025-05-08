pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                script {
                    // Build the Docker image
                    docker.build('my-image')
                }
            }
        }
        stage('Test') {
            steps {
                script {
                    // Run tests inside the Docker container
                    docker.image('my-image').inside {
                        // Your test command here, e.g., running npm tests
                        sh 'npm test'
                    }
                }
            }
        }
    }
}
