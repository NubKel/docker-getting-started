pipeline {
    agent any
    
    stages {
        stage('Clean previous docker') {
            steps {
                sh 'docker kill $(docker ps -q)'
                sh 'docker rm $(docker ps -a -q)'
            }
        }
        stage('Build Docker image') {
            steps {
                sh 'docker build -t docker-getting-started .'
            }
        }

        stage('Run Docker Container') {
            steps {
                sh 'docker run -dp 3000:3000 docker-getting-started'
            }
          }
    }
}
