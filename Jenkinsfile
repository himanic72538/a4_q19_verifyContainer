pipeline {
    agent any
    stages {
        stage('Checkout') {
            steps {
                git 'https://github.com/himanic72538/a4_q19_verifyContainer.git'
            }
        }
        stage('Build Image') {
            steps {
                sh 'docker build -t my-flask-app .'
            }
        }
        stage('Run Container') {
            steps {
                sh 'docker rm -f my-running-app || true'
                sh 'docker run -d -p 5000:5000 --name my-running-app my-flask-app'
            }
        }
        stage('Verify Container') {
            steps {
                sh 'docker ps | grep my-running-app'
            }
        }
    }
}
