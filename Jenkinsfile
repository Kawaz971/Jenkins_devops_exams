pipeline {
    agent any

    environment {
        DOCKERHUB_CREDENTIALS = 'dockerhub'
        DOCKERHUB_USERNAME = 'jaysse'
    }

    stages {
        stage('Build and Push cast-service') {
            steps {
                script {
                    withDockerRegistry(credentialsId: DOCKERHUB_CREDENTIALS, url: '') {
                        dir('cast-service') {
                            sh "docker build -t ${DOCKERHUB_USERNAME}/cast-service:latest ."
                            sh "docker push ${DOCKERHUB_USERNAME}/icast-service:latest"
                        }
                    }
                }
            }
        }

        stage('Build and Push movie-service') {
            steps {
                script {
                    withDockerRegistry(credentialsId: DOCKERHUB_CREDENTIALS, url: '') {
                        dir('movie-service') {
                            sh "docker build -t ${DOCKERHUB_USERNAME}/movie-service:latest ."
                            sh "docker push ${DOCKERHUB_USERNAME}/movie-service:latest"
                        }
                    }
                }
            }
        }
    }
}
