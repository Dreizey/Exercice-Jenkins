pipeline {
    agent {
        docker {
            image 'node:lts-bullseye'
            args '-v $HOME/.npm:/root/.npm:z -u root'
        }
    }
    
    stages {
        stage('Git checkout') {
            steps {
                script {
                    git credentialsId: 'Dreizey',
                        url: 'git@github.com:Dreizey/Exercice-Jenkins.git',
                        branch: 'main'
                }
            }
        }
        
        stage('Docker compose') {
            steps {
                    sh 'docker compose up -d --build'
            }
        }
    }
}