pipeline {
	agent any 
	// agent {docker { image 'node:13.8'}}
	stages {
		stage('build') {
			steps {
			// sh 'node --version'
			echo "build"
			echo "path - $path"
			echo "BUILD_NUMBER - $env.BUILD_NUMBER"
			echo "BUILD_ID - $env.BUILD_ID"
			echo "JOD_NAME - $env.JOD_NAME"
			echo "BUILD_TAG - $env.BUILD_TAG"
			}
		}
		stage('test') {
			steps {
			echo "test"
			}
		}

		stage('integration test') {
			steps {
			echo "integration test"
			}
		}
	}
	post {
		failure {
			echo "i failed i am sorry about that. try again"
		}
	
		always {
			echo "yay i run always" 
		}
	
		success {
			echo "i told you i was going to make it"
		}
	}
}
