pipeline {
    agent any

    stages {
        stage('Build & Tag Docker Image') {
            steps {
                script {
                    withDockerRegistry(credentialsId: 'DockerHubCredentials', toolName: 'docker') {
                        sh "docker build -t sihasaneshubham/productcatalogservice:latest ."
                    }
                }
            }
        }
        
        stage('Push Docker Image') {
            steps {
                script {
                    withDockerRegistry(credentialsId: 'DockerHubCredentials', toolName: 'docker') {
                        sh "docker push sihasaneshubham/productcatalogservice:latest "
                    }
                }
            }
        }
    }
}
