pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                sh 'docker build -t raghusai/emailservice:v1 .'
            }
        }
        stage ("Push"){
            steps {
                script {
                    withDockerRegistry(credentialsId: 'docker-cred') {
                        sh 'docker push raghusai/emailservice:v1'
                    }
                }
            }
        }
    }
}
