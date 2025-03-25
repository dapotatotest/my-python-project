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
        
        stage('Pulish') {
            steps {
                script {
                    sh 'echo $DOCKER_PASS | docker login -u $DOCKER_LOGIN --password-stdin'
                    sh 'docker build -t alianib/my-python-app:$BUILD_NUMBER .'
                    sh 'docker push alianib/my-python-app:$BUILD_NUMBER'
                }
            }
        }
        
    }
}