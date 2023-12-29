pipeline {
    agent any

    stages {
        stage('Build and Push cast-service') {
            steps {
                script {
                    dir('cast-service') {
                        // Commandes de build et de push pour cast-service
                        sh 'docker build -t cast-service .'
                        sh 'docker push cast-service'
                    }
                }
            }
        }

        stage('Build and Push movie-service') {
            steps {
                script {
                    dir('movie-service') {
                        // Commandes de build et de push pour Dockerfile 2
                        sh 'docker build -t movie-service .'
                        sh 'docker push movie-service'
                    }
                }
            }
        }
    }
}
