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
		  sh "chmod u+x docker-hub"
                  withDockerRegistry(credentialsId: '9c641a07-a951-4715-a8f0-6e8ea7cb532b', url: 'https://index.docker.io/v1/') {
    		      sh 'docker build -t dunglen15102001/test:v1 .'
                      sh 'docker push dunglen15102001/test:v1 .'
                  }
              }
        }
    }
}
