pipeline {
    agent any

    stages {
        stage('Build and Push cast-service') {
            steps {
                script {
                    dir('cast-service') {

                        withCredentials([string(credentialsId: 'dockerhub', variable: 'dockerhub')]) {
                        // Commandes de build et de push pour cast-service
                        sh 'docker login -u jaysse -p ${dockerhub}'
                        sh 'docker build -t cast-service .'
                        sh 'docker image tag $JOB_NAME:v1.$BUILD_ID jaysse/$JOB_NAME:v1.$BUILD_ID'
                        sh 'docker image tag $JOB_NAME:v1.$BUILD_ID jaysse/$JOB_NAME:latest'
                        sh 'docker image push jaysse/$JOB_NAME:v1.$BUILD_ID '
                        sh 'docker image push jaysse/$JOB_NAME:latest'
                        }
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