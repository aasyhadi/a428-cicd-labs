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
                sh 'npm install react-scripts --save'
            }
        }
        stage('Test') {
            steps {
                sh './jenkins/scripts/test.sh'
            }
        }
    }
}