pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                script {
                    sh 'python3 -m flake8 . --count --show-source --statistics || true'
                }
            }
        }
    }
}