pipeline {
    agent any

    stages {
        stage('Build and Push cast-service') {
            steps {
                script {
                    dir('cast-service') {
                        // Commandes de build et de push pour cast-service
                    
                        sh 'docker build -t cast-service:v1.$BUILD_ID .'
                        
                    }
                }
            }
        }
    }
}