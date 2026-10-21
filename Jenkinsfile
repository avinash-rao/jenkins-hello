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
                sh '''
                    python3 -m venv .venv
                    .venv/bin/python -m pip install --upgrade pip
                    .venv/bin/python -m pip install pytest
                '''
            }
        }

        stage('Run Unit Tests') {
            steps {
                sh '.venv/bin/python -m pytest -v'
            }
        }
    }
}
