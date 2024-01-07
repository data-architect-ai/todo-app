pipeline {
    agent any
    tools {
        nodejs 'Nodejs 21.5.0'
    }
    stages {
        stage('Build') {
            steps {
                sh 'npm install'
            }
        }
        stage('Test') {
            steps {
                echo 'running test'
                //sh 'npm test'
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

