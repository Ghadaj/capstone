pipeline {
	agent any
	stages {
		stage('build docker image') {
		    steps {
				withCredentials([string(credentialsId: 'docker', variable: 'TOKEN')]) {
				sh '''
					docker build -t ghadaj/capstone .
				'''
				}
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
	    stage('Lint HTML') {
		    steps {
			 sh 'tidy -q -e *.html'
			}
		}
}
