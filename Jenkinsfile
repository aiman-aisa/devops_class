pipeline {
    agent {
        dockerfile true
    }
    stages {
        stage('Build') {
            steps {
                sh 'apt install python3 python3-venv -y'
                sh '''
                    cd /var/jenkins_home/workspace/devops_class_gitlab
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