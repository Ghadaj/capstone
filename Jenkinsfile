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
	}
}
}
