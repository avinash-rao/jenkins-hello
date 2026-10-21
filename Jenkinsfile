pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Install pytest') {
            steps {
                sh 'python3 -m venv .venv'
                sh '.venv/bin/pip install pytest'
            }
        }

        stage('Run Unit Tests') {
            steps {
                sh '.venv/bin/python -m pytest -v'
            }
        }
    }
}
