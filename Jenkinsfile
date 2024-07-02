pipeline {
    agent any

    stage('recommendationservice') {
            steps {
                script {
                    withCredentials([string(credentialsId: 'DockerHubCredentials', variable: 'DockerHubCredentials')]) {
                          sh 'docker login -u charlesjatto -p ${DockerHubCredentials}'
                          sh 'docker build -t charlesjatto/recommendationservice:latest .'
                          sh 'docker push charlesjatto/recommendationservice:latest'
                          sh 'docker rmi charlesjatto/recommendationservice:latest'
                 }
            }
        }
    }
}
