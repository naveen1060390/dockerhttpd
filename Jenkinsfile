
pipeline{
  agent any
   
    stages {
	  stage ('checkout') {
	    steps {
		  echo 'checkingin the pipeline'
		  git 'https://github.com/sforcloud/dockerhttpd.git'
		}
	  }
	  stage  ('build') {
	   steps {
	     echo 'pipeline started building the docker image' 
	     sh 'sudo docker build -t naveenimg .'
	   }
	 } 
	   stage ('tag') {
	     steps {
		   echo 'tagging the names'
		   sh 'sudo docker tag naveenimg dockernh2021/naveen'

		 }	  
	  }
	  
	    stage ('login') {
		  steps {
		     echo 'we are logging into Docker Hub'
			 sh 'sudo docker login -u dockernh2021 -p 9291688567J'
		  }
	  }
	  
	    stage ('push') {
		  steps {
		    echo 'pushing the image to docker hub'
			sh 'sudo docker push dockernh2021/naveen'
		  }
		}
	 
	}
 }
