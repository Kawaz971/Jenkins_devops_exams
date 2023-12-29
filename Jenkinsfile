pipeline {
    agent any

    stages {
        stage('Build and Push cast-service') {
            steps {
                script {
                    dir('cast-service') {
                        withCredentials([string(credentialsId: 'dockerhub_passwd', variable: 'dockerhub_password')]) {
                            sh 'docker build -t cast-service:v1.$BUILD_ID .'
                            sh 'docker image tag cast-service:v1.$BUILD_ID jaysse/cast-service:v1.$BUILD_ID'
                            sh 'docker image tag cast-service:v1.$BUILD_ID jaysse/cast-service:v1.latest'
                            sh 'docker login -u jaysse -p ${dockerhub_password}'
                            sh 'docker image push jaysse/cast-service:v1.$BUILD_ID'
                            sh 'docker image push jaysse/cast-service:v1.latest'

    
                        }
                    
                    
                        
                    }
                }
            }
        }
    }
}