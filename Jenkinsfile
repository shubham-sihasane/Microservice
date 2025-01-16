pipeline {
    agent any

    stages {
        stage('Build & Tag Docker Image') {
            steps {
                script {
                    dir('src') {

                    withDockerRegistry(credentialsId: 'DockerHubCredentials', toolName: 'docker') {
                        sh "docker build -t sihasaneshubham/cartservice:latest ."
                    }
                        }
                }
            }
        }
        
        stage('Push Docker Image') {
            steps {
                script {
                    withDockerRegistry(credentialsId: 'DockerHubCredentials', toolName: 'docker') {
                        sh "docker push sihasaneshubham/cartservice:latest "
                    }
                }
            }
        }
    }
}
