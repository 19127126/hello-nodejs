pipeline{

	agent any

	stages {
	    
	    stage('gitclone') {

			steps {
				git 'https://github.com/19127126/hello-nodejs.git'
			}
		}

		stage('Build and Publish') {

			steps {
				withDockerRegistry(credentialsId: 'dockerhub', url: 'https://index.docker.io/v1/') {
					sh label: '', script: 'docker build -t ductrung1512/test:v1 .'
					sh label: '', script: 'docker push ductrung1512/test:v1'
				}
			}
		}

		
	}


}