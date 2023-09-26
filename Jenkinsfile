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
                echo 'Deploying'
                sh '''
                docker build -t my-python-app .
                docker run -d -p 8089:80 my-python-app
                '''
            }
        }
    }
}
