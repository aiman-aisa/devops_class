pipeline {
    agent none
    stages {
        stage('DB') {
            agent {
                docker { image 'mysql:latest'}
            }
            steps {
                sh 'mysql -V'
            }
        }
        stage('Front-end') {
            agent { dockerfile True }

            steps {
                sh 'node --version'
            }
        }
    }
}