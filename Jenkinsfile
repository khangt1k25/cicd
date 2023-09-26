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
                echo "Building.."
                sh '''
                cd app
                pip install -r requirements.txt
                '''
            }
        }
        stage('Test') {
            steps {
                echo "Testing.."
                sh '''
                cd app
                python test.py
                '''
            }
        }
        stage('Deploy') {
            steps {
                echo "Deploying.."
                // Deploy your application here (e.g., push to a container registry)
            }
        }
    }
}
