pipeline {
    agent {
        docker {
            image 'python:3.8'  // Use the Docker image you specified in your Dockerfile
            args '-u root'      // Run as root to avoid permission issues
        }
    }
    stages {
        stage('Build') {
            steps {
                sh '''
                cd app
                pip install -r requirements.txt
                '''
            }
        }
        stage('Test') {
            steps {
                sh '''
                cd app
                python test.py
                '''
            }
        }
        stage('Deploy') {
            steps {
                // Deploy your application here (e.g., push to a container registry)
            }
        }
    }
}
