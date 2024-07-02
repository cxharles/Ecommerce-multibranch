pipeline {
    agent any

    stages {
        stage('cartservice') {
            steps {
                script {
                    withCredentials([string(credentialsId: 'DockerHubCredentials', variable: 'DockerHubCredentials')]) {
                        dir('src') {
                            sh 'docker login -u charlesjatto -p ${DockerHubCredentials}'
                            sh 'docker build -t charlesjatto/cartservice:latest .'
                            sh 'docker push charlesjatto/cartservice:latest'
                            sh 'docker rmi charlesjatto/cartservice:latest'
                        }
                    }
                }
            }
        }
    }
}
