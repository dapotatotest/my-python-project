pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                script {
                    python3 -m flake8 . --count --show-source --statistics || true
                }
            }
        }
    }
}