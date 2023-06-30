pipeline {
    agent {
        docker {
            image 'python:3.8-alpine'
        }
    }
    stages {
        stage('Build') {
            steps {
                dir('back-end-python') {
                    sh 'pip install -r gameactions/requirements.txt'
                }
            }
        }

        stage('Test') {
            steps {
                dir('back-end-python') {
                    sh 'pip install -r tests/requirements.txt'
                    sh 'python -m pytest tests/unit'
                    sh 'python -m pytest tests/integration'
                }
            }
        }

        stage('Deploy') {
            steps {
                // Add your deployment steps here
                echo "Deploy"
            }
        }
    }
}
