pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                script {
                    sh 'python3 -m venv venv' // Create virtual environment
                    sh './venv/bin/pip install -r requirements.txt' // Install dependencies
                }
            }
        }
        stage('Test') {
            steps {
                script {
                    sh './venv/bin/python -m unittest discover' // Run tests
                }
            }
        }
        stage('Deploy') {  
            steps {
                script {
                    // Simulate deployment (e.g., copying build artifacts)
                    echo "Simulating deployment of artifacts..."
                }
            }
        }
    }
    post {
        always {
            deleteDir() // Clean up workspace
        }
    }
}
