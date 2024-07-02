pipeline {
    agent any

    stages {
        stage('checkoutservice') {
            steps {
                script {
                    withCredentials([string(credentialsId: 'DockerHubCredentials', variable: 'DockerHubCredentials')]) {
                        sh 'docker login -u charlesjatto -p ${DockerHubCredentials}'
                        sh 'docker build -t charlesjatto/checkoutservice:latest .'
                        sh 'docker push charlesjatto/checkoutservice:latest'
                        sh 'docker rmi charlesjatto/checkoutservice:latest'
                    }
                }
            }
        }
    }
}
