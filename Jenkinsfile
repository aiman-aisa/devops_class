pipeline {
    agent any
    stages {
        stage('Build') {
            agent {
                docker { 
                    image 'docker:cli'
                    args '--privileged'
                    }
            }
            steps {
                sh 'docker compose --version'
                sh 'docker compose -f docker-compose.yml up -d'
                sh 'docker compose ps'
            }
        }
        stage('Test') {
            agent {
                docker { 
                    image 'docker:cli'
                    args '--privileged'
                    }
            }
            steps {
                sh 'docker compose --version'
                sh 'docker compose -f docker-compose.yml up -d'
                sh 'docker compose ps'
            }
        }
    }
}