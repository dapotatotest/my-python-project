pipeline {
    agent any
    stages {
        stage('Flake8') {
            steps {
                script {
                    sh 'python3 -m flake8 . --count --show-source --statistics || true'
                }
            }
        }
        stage('Test') {
            steps {
                script {
                    sh 'pytest | tee report.txt'
                }
            }
        }

        
    }
}