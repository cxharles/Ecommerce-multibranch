pipeline {
    agent any

    stage('emailservice') {
            steps {
                script {
                    withCredentials([string(credentialsId: 'DockerHubCredentials', variable: 'DockerHubCredentials')]) {
                          sh 'docker login -u charlesjatto -p ${DockerHubCredentials}'
                          sh 'docker build -t charlesjatto/emailservice:latest .'
                          sh 'docker push charlesjatto/emailservice:latest'
                          sh 'docker rmi charlesjatto/emailservice:latest'
                }
             }
        }
    }
}
