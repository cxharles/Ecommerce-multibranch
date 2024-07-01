pipeline {
    agent any

    stage('checkoutservice') {
            steps {
                script {
                    withCredentials([string(credentialsId: 'DockerHubCredentials', variable: 'DockerHubCredentials')]) {
                       dir('/var/lib/jenkins/workspace/10-Tier/src/checkoutservice') {
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
