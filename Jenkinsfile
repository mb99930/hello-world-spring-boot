pipeline {
	agent any
	tools {
        maven 'maven-3.6.3' 
        }
		
	stages {

    stage('Build Docker Image'){
     steps {		
			bat 'docker build -t nginx:1.0.1 .'
		}
   }
   
     stage('Push NGINX Docker Image'){
		steps {
        	echo 'connecting to ECR.. '
           withDockerRegistry([url: "https://310643530327.dkr.ecr.us-west-2.amazonaws.com/nginx",credentialsId: "ecr:us-west-2:aws-credentials"]) {
           bat 'docker tag nginx:1.0.1 310643530327.dkr.ecr.us-west-2.amazonaws.com/nginx:1.0.1'
	   bat 'docker push 310643530327.dkr.ecr.us-west-2.amazonaws.com/nginx:1.0.1'
               }
	    }
	}

}
}
