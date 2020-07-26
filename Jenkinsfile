pipeline {
	agent any
	stages {
		stage('build and push docker image') {
		    steps {
    					sh '''
					  sudo docker login -u ghadaj -p Ghada153
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
