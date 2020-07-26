pipeline {
	agent any
	stages {
		stage('build and push docker image') {
			steps {
				withAWS(region:'us-west-2', credentials:'aws') {
				sh '''
				eksctl create cluster \
				--name mycluster \
				--version 1.17 \
				--region us-west-2 \
				--nodegroup-name linux-nodes \
				--node-type t3.medium \
				--nodes 3 \
				--nodes-min 1 \
				--nodes-max 4 \
				}
		    }
	}
}
}
