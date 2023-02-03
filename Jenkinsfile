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
			echo "$path"
			echo "BUILD_NUMBER - $env.BUILD_NUMBER"
			ech0 "$env.BUILD_ID"
			ech0 "$env.JOD_NAME"
			ech0 "$env.BUILD_TAG"
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
