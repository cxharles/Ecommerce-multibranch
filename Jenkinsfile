pipeline {
    agent any

    stages {
        stage('loadgenerator') {
            steps {
                script {
                    withCredentials([string(credentialsId: 'DockerHubCredentials', variable: 'DockerHubCredentials')]) {
                        sh 'docker login -u charlesjatto -p ${DockerHubCredentials}'
                        sh 'docker build -t charlesjatto/loadgenerator:latest .'
                        sh 'docker push charlesjatto/loadgenerator:latest'
                        sh 'docker rmi charlesjatto/loadgenerator:latest'
                    }
                }
            }
        }
    }
}
