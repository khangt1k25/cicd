pipeline {
    agent {
        node {
            label 'docker-agent-python'
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
                python3 test.py
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
