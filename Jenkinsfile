pipeline {
    agent any
    
    stages {
        stage('Build Docker image') {
            steps {
                sh 'docker kill $(docker ps -q)'
                sh 'docker rm $(docker ps -a -q)'

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
