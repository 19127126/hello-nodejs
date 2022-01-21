pipeline{
    agent any
    stages{
        stage('Clone'){
              steps{
                  git 'https://github.com/19127126/hello-nodejs.git'
              }
         }
        stage('Build image and push to Dockerhub'){
              steps{
                  withDockerRegistry(credentialsId: 'docker-hub', url: 'https://index.docker.io/v1/') {
    		      sh label: '', script: 'docker build -t dunglen15102001/test:v1 .'
                      sh label: '', script: 'docker push dunglen15102001/test:v1'
              }
         }
     }
}
