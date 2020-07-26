pipeline {
	agent any
	stages {

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
