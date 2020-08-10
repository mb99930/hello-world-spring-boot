pipeline {
	agent any
	tools {
        maven 'maven-3.6.3' 
        }
		
	stages {
	stage('Running Fargate Task') {
		steps {
				echo 'Running fargate task'
		withCredentials([[$class: 'AmazonWebServicesCredentialsBinding', accessKeyVariable: 'AWS_ACCESS_KEY_ID', credentialsId: 'aws-credentials', secretKeyVariable: 'AWS_SECRET_ACCESS_KEY']]) {
    
			cfnUpdate(stack:'my-stack', file:'fargate.yaml')
			echo 'cfnupdate finished'
	}
		}
		}
}
}
