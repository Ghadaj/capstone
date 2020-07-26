pipeline {
	agent any
	stages {
		stage('Build docker image') {
		    steps {
			    script{	
				    docker.withRegistry('https://registry.hub.docker.com','docker') {
					def customImage = docker.build("ghadaj/mydockerwebapp")
				      //customImage.push()
			    }
			}
		    }
		}
		stage('Push docker image') {
		    steps {
			    script{	
				    docker.withRegistry('https://registry.hub.docker.com','docker') {
					customImage.push()
			    }
			}
		    }
		}
		stage('Deploy kubect') {
			steps {
				withAWS(region:'us-west-2', credentials:'aws') {
					sh '''
						 kubectl apply -f deployment.yml
					#sh 'sudo kubectl apply -f ./deployments/load-balancer.yml'
					'''
				}
			}
		}
	}
}
