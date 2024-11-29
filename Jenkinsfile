pipeline {
    agent any
         
    stages {
        stage('Build image') {
            steps {
                    sh 'docker build -t yunandar711/todo-app:${BUILD_ID} .'
                    sh 'docker images'
                }
        }


        stage('Deploy to Server') {
            steps {
                script {
                    def gitClone = 'git clone https://github.com/yunandarz/todo-app.git'
                    def dockerPull = 'docker pull yunandar711/todo-app'
                    def dockerComposeDown = 'docker compose down --volumes'
                    def deleteImages = 'docker image prune -a --force'
                    def dockerComposeUp = 'docker compose up -d'

                    sh "${gitClone} && ${dockerPull}"
                    sh "${dockerComposeDown}"
                    sh "${deleteImages}"
                    sh "cd todo-app && ${dockerComposeUp}"

                    
                   
                    
                }
            }
        }

        
    }
    
}
