pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                script {
                    // Install dependencies
                    sh 'python3 -m venv venv'
                    sh './venv/bin/pip install -r requirements.txt'
                }
            }
        }
        stage('Test') {
            steps {
                script {
                    // Run tests (if any)
                    sh './venv/bin/python -m unittest discover'
                }
            }
        }
        stage('Deploy') {
            steps {
                script {
                    // Deploy the application
                    sh '''
                    docker build -t yourusername/my-python-app:latest .
                    docker run -d -p 5000:5000 yourusername/my-python-app:latest
                    '''
                }
            }
        }
    }

    post {
        always {
            // Clean up workspace
            deleteDir()
        }
        success {
            echo 'Pipeline completed successfully!'
        }
        failure {
            echo 'Pipeline failed!'
        }
    }
}
