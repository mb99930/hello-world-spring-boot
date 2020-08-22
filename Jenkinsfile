pipeline {
	agent any
	tools {
        maven 'maven-3.6.3' 
        }
	environment {
		version = "${BUILD_NUMBER}"
	}	
	stages {

    stage('Build Docker Image'){
     steps {	
     		echo "Current Build Number is : ${BUILD_NUMBER}"
     		echo "Current Build Number is : ${version}"

 			bat 'docker build clx-repx:${version} .'
		}
   }
}
}
