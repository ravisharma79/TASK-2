pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building Docker image...'
                sh 'docker build -t nodejs-demo-app .'
            }
        }

        stage('Test') {
            steps {
                echo 'Deploying app...'
                sh 'docker rm -f nodejs-demo-app || true'
                sh 'docker run -d -p 3000:3000 --name nodejs-demo-app nodejs-demo-app'
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploying app...'
                sh 'docker run -d -p 3000:3000 --name nodejs-demo-app nodejs-demo-app'
            }
        }
    }
}
