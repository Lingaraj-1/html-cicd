pipeline {
    agent any

    stages {
        stage('Clone Repo') {
            steps {
                git branch: 'main',
                    url: 'https://github.com/Lingaraj-1/html-cicd.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t html-app .'
            }
        }

        stage('Run Container') {
            steps {
                sh '''
                docker stop html-app || true
                docker rm html-app || true
                docker run -d -p 8081:80 --name html-app html-app
                '''
            }
        }
    }
}

