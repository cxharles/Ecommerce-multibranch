pipeline {
    agent any

    stages {
        stage('productcatalogservice') {
            steps {
                script {
                    withCredentials([string(credentialsId: 'DockerHubCredentials', variable: 'DockerHubCredentials')]) {
                        sh 'docker login -u charlesjatto -p ${DockerHubCredentials}'
                        sh 'docker build -t charlesjatto/productcatalogservice:latest .'
                        sh 'docker push charlesjatto/productcatalogservice:latest'
                        sh 'docker rmi charlesjatto/productcatalogservice:latest'
                    }
                }
            }
        }
    }
}
