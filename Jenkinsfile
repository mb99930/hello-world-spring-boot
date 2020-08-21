pipeline {
	agent any
	tools {
        maven 'maven-3.6.3' 
        }
		
	stages {

    stage('Build Docker Image'){
     steps {		
			bat 'docker build -t clx-repx:${env.BUILD_ID} .'
		}
   }


}
}
