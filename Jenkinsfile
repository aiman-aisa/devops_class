pipeline {
    agent {
        dockerfile true
    }
    stages {
        stage('Build') {
            steps {
                sh '''
                    cd DevopsClassFront
                    docker build -t frontend .
                    docker run -d -p 80:80 frontend
                '''
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