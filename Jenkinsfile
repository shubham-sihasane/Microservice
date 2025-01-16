pipeline {
    agent any

    stages {
        stage('Build & Tag Docker Image') {
            steps {
                script {
                    withDockerRegistry(credentialsId: 'DockerHubCredentials', toolName: 'docker') {
                        sh "docker build -t sihasaneshubham/currencyservice:latest ."
                    }
                }
            }
        }
        
        stage('Push Docker Image') {
            steps {
                script {
                    withDockerRegistry(credentialsId: 'DockerHubCredentials', toolName: 'docker') {
                        sh "docker push sihasaneshubham/currencyservice:latest "
                    }
                }
            }
        }
    }
}
