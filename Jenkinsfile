pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                script {
                    sh 'python3 -m venv venv'
                    sh './venv/bin/pip install -r requirements.txt'
                }
            }
        }
        stage('Test') {
            steps {
                script {
                    sh './venv/bin/python -m unittest discover'
                }
            }
        }
        stage('Deploy') {
            steps {
                script {
                    sh 'docker build -t yourusername/my-python-app:latest .'
                }
            }
        }
    }
    post {
        always {
            deleteDir()
        }
    }
}