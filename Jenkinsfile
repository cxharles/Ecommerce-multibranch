pipeline {
    agent any

    stages {
        stage('shippingservice') {
            steps {
                script {
                    withCredentials([string(credentialsId: 'DockerHubCredentials', variable: 'DockerHubCredentials')]) {
                        sh 'docker login -u charlesjatto -p ${DockerHubCredentials}'
                        sh 'docker build -t charlesjatto/shippingservice:latest .'
                        sh 'docker push charlesjatto/shippingservice:latest'
                        sh 'docker rmi charlesjatto/shippingservice:latest'
                    }
                }
            }
        }
    }
}
