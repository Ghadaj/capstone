pipeline {
	agent any
	stages {
		stage('Set current kubectl context') {
			steps {
				withAWS(region:'us-west-2', credentials:'aws') {
					sh '''
						kubectl config use-context arn:aws:eks:us-west-2:433927923947:cluster/ekscluster
					'''
				}
			}
		}
		stage('Deploy kubectl context') {
			steps {
				withAWS(region:'us-west-2', credentials:'aws') {
					sh '''
						kubectl run my-pod --image=ghadaj/mydockerwebapp:latest --port=80 
						kubectl get pod --all-namespaces --no-headers
						kubectl port-forward my-pod  8000:80
					'''
				}
			}
		}
	}
}
