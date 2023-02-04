pipeline {
	agent any 
	// agent {docker { image 'node:13.8'}}
	stages {
		stage('build') {
			steps {
			echo"build"
			}
		}
		stage('test') {
			steps {
			echo "test"
			// sh 'node --version'
			echo "path - $path"
			echo "BUILD_NUMBER - $env.BUILD_NUMBER"
			ech0 "BUILD_ID - $env.BUILD_ID"
			ech0 "JOD_NAME - $env.JOD_NAME"
			ech0 "BUILD_TAG - $env.BUILD_TAG"
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
