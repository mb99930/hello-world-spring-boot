pipeline {
	agent any
	tools {
        maven 'maven-3.6.3' 
        }
		
	stages {

    stage('Build Docker Image'){
     steps {
	     		echo "Current Build Number is : ${BUILD_NUMBER}"
			//bat 'docker build -t clx-repx:"${BUILD_NUMBER}" .'
		}
   }
   


}
}
