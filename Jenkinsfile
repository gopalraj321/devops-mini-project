pipeline {
    agent any

    stages {
        stage('Clone Repo') {
            steps {
                git 'https://github.com/YOUR_USERNAME/devops-mini-project.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t devops-mini-app .'
            }
        }

        stage('Stop Existing Container') {
            steps {
                sh '''
                docker stop devops-mini-app || true
                docker rm devops-mini-app || true
                '''
            }
        }

        stage('Run Docker Container') {
            steps {
                sh 'docker run -d -p 5000:5000 --name devops-mini-app devops-mini-app'
            }
        }
    }
}
