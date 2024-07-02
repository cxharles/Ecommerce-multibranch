pipeline {
    agent any

    stage('frontend') {
            steps {
                script {
                    withCredentials([string(credentialsId: 'DockerHubCredentials', variable: 'DockerHubCredentials')]) {  
                          sh 'docker login -u charlesjatto -p ${DockerHubCredentials}'
                          sh 'docker build -t charlesjatto/frontend:latest .'
                          sh 'docker push charlesjatto/frontend:latest'
                          sh 'docker rmi charlesjatto/frontend:latest'
                 }
             }
          }
     }
}
