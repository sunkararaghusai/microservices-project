pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                sh 'docker build -t raghusai/recommendationservice:v1 .'
            }
        }
        stage ("Push"){
            steps {
                script {
                    withDockerRegistry(credentialsId: 'docker-cred') {
                        sh 'docker push raghusai/recommendationservice:v1'
                    }
                }
            }
        }
    }
}
