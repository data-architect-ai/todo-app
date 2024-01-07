pipeline {
    agent any
    tools {
        nodejs 'Nodejs 21.5.0'
    }
    stages {
        stage('Build') {
            steps {
                sh 'npm install && yarn install --production'
            }
        }
        stage('Test') {
            steps {
                sh './jenkins/script/test.sh'
            }
        }
        stage('Deploy') {
            steps {
                sh './jenkins/script/deliver.sh' 
                sh 'sleep 1m'
                input message: 'visit http://localhost:3000 to see your application'
            }
        }
    }
}
