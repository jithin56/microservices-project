pipeline {
    agent any

    stages {
        stage('Build & Tag Docker Image') {
            steps {
                sh "docker build -t jithin56/recommendationservice:latest ."
            }
        }
        
        stage('Push Docker Image') {
            steps {
                script {
                    withDockerRegistry(credentialsId: 'docker-cred', toolName: 'docker') {
                        sh "docker push jithin56/recommendationservice:latest "
                    }
                }
            }
        }
    }
}
