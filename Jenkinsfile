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
        stage('Deploy') {  // Renamed for clarity
            steps {
                script {
                    // Simulate deployment (e.g., copying build artifacts)
                    sh 'cp -r build/ artifacts/'  // Replace paths if needed
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
