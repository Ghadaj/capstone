pipeline {
	agent any
	environment {
		registry = "ghadaj/capstone"
	    	registryCredential = ‘docker’
}
	stages {
		stage('build docker image') {
		    steps {

			 docker.build registry + ":$BUILD_NUMBER" .
				
			}
		}
		stage('push docker image') {
		    steps {
			 sh '''
				docker login -u ghadaj -p Ghada153
				docker push ghadaj/capstone
			 '''
			}
		}		
	    stage('Lint') {
		    steps {
			 sh 'tidy -q -e *.html'
			}
		}
}
}
