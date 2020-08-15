pipeline {
	agent any
	tools {
        maven 'maven-3.6.3' 
        }
		
	stages {


     stage('Push NGINX Docker Image'){
		steps {
        	echo 'connecting to ECR.. '
           withDockerRegistry([url: "https://310643530327.dkr.ecr.us-west-2.amazonaws.com/nginx",credentialsId: "ecr:us-west-2:aws-credentials"]) {
           bat 'docker tag nginx:latest 310643530327.dkr.ecr.us-west-2.amazonaws.com/nginx:latest'
	   bat 'docker push 310643530327.dkr.ecr.us-west-2.amazonaws.com/nginx:latest'
               }
	    }
	}

}
}
