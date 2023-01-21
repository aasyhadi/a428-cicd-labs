pipeline {
    agent {
        docker {
            image 'node:lts-bullseye-slim'
            args '-p 8000:8000'
        }
    }
    stages {
        stage('Build') {
            steps {
                sh 'npm install'
            }
        }
        stage('Test') {
            steps {
                sh 'sudo ./jenkins/scripts/test.sh'
            }
        }
    }
}