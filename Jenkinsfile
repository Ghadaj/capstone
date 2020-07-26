pipeline {
	agent any
	stages {
		stage('build docker image') {
		    steps {
  			withDockerRegistry([credentialsId: 'docker', url: "https://hub.docker.com/repository/docker/ghadaj/capstone/"]) {
    					sh '''
  					    docker build -t dockerimg .
  					    docker push dockerimg
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

	 
	}
}
