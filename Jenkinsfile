pipeline {
    agent any

    stages {
        stage('paymentservice') {
            steps {
                script {
                    withCredentials([string(credentialsId: 'DockerHubCredentials', variable: 'DockerHubCredentials')]) {
                        sh 'docker login -u charlesjatto -p ${DockerHubCredentials}'
                        sh 'docker build -t charlesjatto/paymentservice:latest .'
                        sh 'docker push charlesjatto/paymentservice:latest'
                        sh 'docker rmi charlesjatto/paymentservice:latest'
                    }
                }
            }
        }
    }
}
