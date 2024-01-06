pipeline {
    agent any
    tools {
        nodejs 'node:18-alpine'
    }
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
        stage('Deploy') {
            steps {
                sh './jenkins/scripts/deliver.sh' 
                sh 'sleep 1m'
                input message: 'visit http://localhost:3000 to see your application'
            }
        }
    }
}

