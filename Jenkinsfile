pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                sh 'python3 -m venv venv'
                sh './venv/bin/pip install -r requirements.txt'
            }
        }
        stage('Test') {
            steps {
                sh './venv/bin/python -m unittest discover'
            }
        }
        stage('Deploy') {
            steps {
                sh 'docker --version' // Verify Docker is available
                sh 'docker build -t saip/my-python-app:latest .'
            }
        }
    }
    post {
        always {
            deleteDir()
        }
    }
}