pipeline {
    agent any

    stage('currencyservice') {
            steps {
                script {
                    withCredentials([string(credentialsId: 'DockerHubCredentials', variable: 'DockerHubCredentials')]) {
                          sh 'docker login -u charlesjatto -p ${DockerHubCredentials}'
                          sh 'docker build -t charlesjatto/currencyservice:latest .'
                          sh 'docker push charlesjatto/currencyservice:latest'
                          sh 'docker rmi charlesjatto/currencyservice:latest'
                }
             }
        }
    }
}
