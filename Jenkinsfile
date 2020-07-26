pipeline {
	agent any
	stages {
		stage('build and push docker image') {
		    steps {
			    script{	docker.withRegistry('https://registry.hub.docker.com','docker') {
					def customImage = docker.build("ghadaj/mydockerwebapp")
					customImage.push()
			    }
				}
		    }
	}
}
}
