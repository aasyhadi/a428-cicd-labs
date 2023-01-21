pipeline {
    agent {
        docker {
            image 'node:lts-bullseye-slim'
            args '-p 8000:8000'
        }
    }
    env.NODEJS_HOME = "${tool '17'}"
    env.PATH = "${env.NODEJS_HOME}/bin:${env.PATH}"
    env.NODE_TLS_REJECT_UNAUTHORIZED = 0
    stages {
        stage('Build') {
            steps {
                sh 'npm install'
            }
        }
        stage('Test') {
            steps {
                sh './jenkins/scripts/test.sh'
            }
        }
    }
}