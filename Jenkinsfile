pipeline {
	agent any
	tools {
        maven 'maven-3.6.3' 
        }
	environment {
		version = "${BUILD_NUMBER}"
		project = 'clxrepx'
		image = "$project:$version"
	}	
	stages {

    stage('Build Docker Image'){
     steps {	
     		echo "Current Build Number is : ${BUILD_NUMBER}"
     		echo "Current Build Number is : ${version}"
     		echo "Current Image Name is : ${image}"

 			bat 'docker build -t clxrepx .'
		}
   }
   
     stage('Push NGINX Docker Image'){
		steps {
        	echo 'connecting to ECR.. '
           withDockerRegistry([url: "https://310643530327.dkr.ecr.us-west-2.amazonaws.com/clxrepx",credentialsId: "ecr:us-west-2:aws-credentials"]) {
		   bat 'docker tag clxrepx:${version} 310643530327.dkr.ecr.us-west-2.amazonaws.com/clxrepx'
   		  bat 'docker push 310643530327.dkr.ecr.us-west-2.amazonaws.com/clxrepx'

               }
	    }
	}

}
}
