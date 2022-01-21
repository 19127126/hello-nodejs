pipeline{
  agent{
    dockerfile {
            filename 'Dockerfile.jenkinsAgent'
            args '-v /var/run/docker.sock:/var/run/docker.sock'
        }
    stages{
        stage('Clone'){
              steps{
                  git 'https://github.com/19127126/hello-nodejs.git'
              }
        }
        stage('Build image and push to Dockerhub'){
              steps{
		  sh "chmod u+x docker-hub"
                  withDockerRegistry(credentialsId: 'docker-hub', url: 'https://index.docker.io/v1/') {
    		      sh 'docker build -t dunglen15102001/test:v1 .'
                      sh 'docker push dunglen15102001/test:v1 .'
                  }
              }
        }
    }
  }
}
