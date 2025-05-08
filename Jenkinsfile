pipeline {
    agent any
    stages {
        stage('Build & Push') {
            steps {
                bat 'docker build -t tanishkagoyal/my-html-site . && docker push tanishkagoyal/my-html-site'
            }
        }
    }
}
