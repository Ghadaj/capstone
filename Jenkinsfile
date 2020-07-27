pipeline {
environment {

        customImage = ''
    }
	agent any
	stages {
		 stage('Lint HTML') {
			    steps {
				    sh 'tidy -q -e *.html'
			    }
		    }
		stage('Build docker image') {
		    steps {
			    script{	
				    docker.withRegistry('https://registry.hub.docker.com','docker') {
					customImage = docker.build("ghadaj/mydockerwebapp")
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
		
	/*	stage('Build Kubernetes Cluster'){
			steps {
				withAWS(region:'us-west-2', credentials:'aws') {
			    		sh 'kubectl config use-context arn:aws:iam::433927923947:role/eksctl-windows-prod-cluster-ServiceRole-XJK4LJAC55FA'
				}
			}
		    } */
		stage('Deploy kubect') {
			steps {
				withAWS(region:'us-west-2', credentials:'aws') {
					sh '''
						sudo kubectl apply -f  deployment.yml 
					 	sudo kubectl apply -f load-balancer.yml
					'''
				}
			}
		}
	}
}
