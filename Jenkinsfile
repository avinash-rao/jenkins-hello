pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Run Unit tests') {
            agent {
                docker {
                    image 'python:3.12-slim'
                }
            }
            
            steps {
                sh 'python -m pip install pytest'
                sh 'python3 -m pytest -v'
            }
        }
    }
}
