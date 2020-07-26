pipeline {
	agent any
	stages {
		stage('build and push docker image') {
		    steps {
  			withDockerRegistry([credentialsId: 'docker', url: "https://hub.docker.com/repository/docker/ghadaj/capstone/"]) {
    					sh '''
  					  # FROM nginx:mainline-alpine
					  # RUN rm /etc/nginx/conf.d/*
					  # ADD hello.conf /etc/nginx/conf.d/
					  # ADD index.html /usr/share/nginx/html/
					  echo "HI"
 				   '''
 				 }
			}
		}
	 
	}
}
