pipeline {
	agent any
	stages {

		stage('Deploy kubectl context') {
			steps {
				withAWS(region:'us-west-2', credentials:'aws') {
					sh '''
						sudo kubectl apply -f ./deployment.yml
					#sh 'sudo kubectl apply -f ./deployments/load-balancer.yml'
					'''
				}
			}
		}
	}
}
