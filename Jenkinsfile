pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                sh 'docker build -t raghusai/cartservice:v1 microservices-project/src/services/'
            }
        }
        stage ("Push"){
            steps {
                script {
                    withDockerRegistry(credentialsId: 'docker-cred') {
                        sh 'docker push raghusai/cartservice:v1'
                    }
                }
            }
        }
    }
}
