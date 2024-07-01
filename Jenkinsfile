pipeline {
    agent any

    stage('adservice') {
            steps {
                script {
                    withCredentials([string(credentialsId: 'DockerHubCredentials', variable: 'DockerHubCredentials')]) {
                       dir('/var/lib/jenkins/workspace/10-Tier/src/adservice') {
                          sh 'docker login -u charlesjatto -p ${DockerHubCredentials}'
                          sh 'docker build -t charlesjatto/adservice:latest .'
                          sh 'docker push charlesjatto/adservice:latest'
                          sh 'docker rmi charlesjatto/adservice:latest'
                    }
                }
            }
        }
    }
}
